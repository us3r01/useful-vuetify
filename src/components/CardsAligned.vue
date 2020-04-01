<template>
    <div>
        <section class="grey lighten-3">
            <v-container>
                <v-row>
                    <v-col v-for="(item, i) in cards" :key="i" cols="12" class="text-center mb-5" md="4">
                        <v-card @click.stop="item.dialog = true" hover class="mx-auto" data-aos="fade-up" max-width="400">
                            <v-img class="white--text align-center" height="200px" gradient="to top, rgba(53, 127, 213, .6), rgba(114,164,174, .6)" :src="item.image">
                                <v-card-title>{{item.titulo}}</v-card-title>
                            </v-img>
                            <v-card-subtitle>
                                {{item.subtitulo}}
                            </v-card-subtitle>
                            <v-card-text>
                                <ul style="list-style: none;">
                                    <li v-for="(bullets,i) in item.bullets" :key="i">
                                        {{bullets}}
                                    </li>
                                </ul>
                            </v-card-text>
                            <v-card-actions>
                                <v-btn color="primary" dark @click.stop="item.dialog = true">
                                    Explore
                                </v-btn>
                            </v-card-actions>
                        </v-card>
    
                        <v-dialog v-model="item.dialog" max-width="560" max-height="315" width="auto" height="auto">
                            <ObjectWithinDialog :description="item.dialog_object" />
                            <v-spacer></v-spacer>
                            <v-btn color="primary" @click="item.dialog = false">
                                Close
                            </v-btn>
                        </v-dialog>
                    </v-col>
                </v-row>
            </v-container>
        </section>
    </div>
</template>

<script>
import ObjectWithinDialog from '@/components/ObjectWithinDialog'
export default {
    components: {
        ObjectWithinDialog
    },

    data: () => ({
        on: true,
        cards: [{
                titulo: 'First Product',
                subtitle: 'Short description',
                image: '/static/kitty_1.png',
                bullets: [
                    'Awesome feature',
                    'Awesome feature',
                    'Awesome feature',
                    'Awesome feature',
                ],
                dialog_object: 'Hello I am item 1',
                dialog: false,
            },
            {
                titulo: 'Second Product',
                subtitle: 'Short description',
                image: '/static/kitty_2.png',
                bullets: [
                    'Awesome feature',
                    'Awesome feature',
                    'Awesome feature',
                    'Awesome feature',
                ],
                dialog_object: 'Hello I am item 2',
                dialog: false,
            },
            {
                titulo: 'Third Product',
                subtitle: 'Short description',
                image: '/static/kitty_3.png',
                bullets: [
                    'Awesome feature',
                    'Awesome feature',
                    'Awesome feature',
                    'Awesome feature',
                ],
                dialog_object: 'Hello I am item 3',
                dialog: false,
            },
        ]
    }),


}
</script>

<style scoped>

</style>