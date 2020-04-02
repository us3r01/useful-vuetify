<template>
    <div>
        <v-sheet :height="$vuetify.breakpoint.xsOnly ? '100vh' : '80vh'">
            <v-container class="fill-height" fluid>
                <v-row class="fill-height" fluid align="center" justify="center">
                    <v-col cols="12" sm="8" md="4" class="text-center">
                        <v-btn large @click="dialog = true" color="primary">
                            Calendar and events example
                        </v-btn>
                        <v-dialog v-model="dialog" width="auto" height="auto">
                            <v-card class="ma-3 pa-3" width="auto" height="auto">
                                <v-card-title>
                                    {{this.currentMonth+ ", " + this.currentYear}}
                                </v-card-title>
                                <v-calendar ref="calendar" :now="today" :value="today" locale="es-MX" :events="events" @click:event="showEvent" color="primary"></v-calendar>
                                <v-menu v-model="selectedOpen" :close-on-content-click="false" :activator="selectedElement" offset-x>
                                    <v-card color="grey lighten-4" min-width="350px" flat>
                                        <v-toolbar :color="selectedEvent.color" dark>
                                            <v-icon class="pr-2">mdi-cake</v-icon>
    
                                            <v-toolbar-title v-html="selectedEvent.name"></v-toolbar-title>
                                            <v-spacer></v-spacer>
    
                                        </v-toolbar>
                                        <v-card-text>
                                            <span v-html="selectedEvent.details"></span>
                                        </v-card-text>
                                        <v-card-actions>
                                            <v-btn text color="secondary" @click="selectedOpen = false">
                                                Cerrar
                                            </v-btn>
                                        </v-card-actions>
                                    </v-card>
                                </v-menu>
                                <v-card-actions>
                                    <v-btn color="primary" dark large @click="dialog = false">
                                        Cerrar
                                    </v-btn>
                                </v-card-actions>
                            </v-card>
                        </v-dialog>
                    </v-col>
                </v-row>
            </v-container>
        </v-sheet>
    </div>
</template>

<script>
// eslint-disable-next-line no-unused-vars
import moment from 'moment';

export default {
    data() {
        return {
            dialog: false,
            selectedEvent: {},
            selectedElement: null,
            selectedOpen: false,
            events: [],
            today: "",
            currentMonth: "",
            currentYear: "",
        }
    },
    methods: {
        showEvent({ nativeEvent, event }) {
            const open = () => {
                this.selectedEvent = event
                this.selectedElement = nativeEvent.target
                setTimeout(() => this.selectedOpen = true, 10)
            }

            if (this.selectedOpen) {
                this.selectedOpen = false
                setTimeout(open, 10)
            } else {
                open()
            }

            nativeEvent.stopPropagation()
        }
    },
    mounted() {
        const moment = require('moment')
        this.currentYear = moment().year();
        var l_date = moment().format("YYYY-MM-DD")
        this.today = l_date;
        moment.locale('es');
        this.currentMonth = moment().month();
        this.currentMonth = moment().month(this.currentMonth);
        var localeData = moment.localeData('es');
        this.currentMonth = localeData.months(this.currentMonth);
        var birthday = this.today;
        birthday = moment().add(7, 'days');
        birthday = moment(birthday).format("YYYY-MM-DD");
        var objt = {
            name: "Johns' Birthday",
            start: birthday,
            details: "<strong>HTML Details of this event</strong>"
        };
        this.events.push(objt);
    },
}
</script>

<style lang="scss" scoped>

</style>