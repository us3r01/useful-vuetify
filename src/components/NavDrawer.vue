<template>
    <v-navigation-drawer v-model="inputValue" fixed left temporary>
        <v-row align="center" class="ma-0 pa-3 flex-no-wrap">
            <v-img contain src="/static/crypto_kitty.svg" width="auto" />
            <v-spacer></v-spacer>
            <v-btn aria-label="Close" class="ml-4" icon @click="toggleDrawer">
                <v-icon>mdi-close</v-icon>
            </v-btn>
        </v-row>
        <v-divider />
        <v-list>
            <v-list-item 
            v-for="(item, i) in drawer_items" 
            :key="i" 
            :to="{path: item.to, params: {meta: isSigned}}"
            :disabled="isSigned ? false : (i != 0)"
            >
                <v-icon class="pr-5">{{item.icon}}</v-icon>
                <v-list-item-title v-text="item.text" />
            </v-list-item>
        </v-list>
    </v-navigation-drawer>
</template>

<script>
// Utilities
import { mapActions, mapGetters } from 'vuex'

export default {
    data: () => ({
        input: false,
        drawer_items: [{
                'to': '/',
                'text': 'Home',
                icon: 'mdi-home'
            },
            {
                'to': '/videos',
                'text': 'Videos',
                icon: 'mdi-video-vintage'
            },
            {
                'to': '/images',
                'text': 'Images',
                icon: 'mdi-image-multiple'
            },
            {
                'to': '/media',
                'text': 'Social',
                icon: 'mdi-star'
            },
            {
                'to': '/playlists',
                'text': 'Music',
                icon: 'mdi-music'
            }
        ]
    }),

    computed: {
        ...mapGetters({
            isSigned: "auth/isSigned",
            drawer: "auth/drawer"
        }),
        inputValue: {
        get() {
            return this.drawer
        },
        set(val) {
            this.setDrawer(val)
        }
        }
    },

    methods: {
        ...mapActions({
            setDrawer: "auth/set_drawer",
            toggleDrawer: "auth/toggle_drawer" //also supports payload `this.nameOfAction(amount)` 
    })

    }
}
</script>
