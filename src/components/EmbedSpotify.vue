<template>
    <div>
        <section class="grey lighten-3">
    
            <v-container>
                <v-row class="text-center">
                    <v-col class="text-center">
                        <h1>Spotify Playlists</h1>
                    </v-col>
                </v-row>
                <v-tabs show-arrows grow v-model="tab" background-color="white" color="blue accent-4">
                    <v-tab v-for="item in items" :key="item.tab">
                        {{ item.tab }}
                    </v-tab>
                </v-tabs>
    
                <v-tabs-items v-model="tab" background-color="transparent">
                    <v-tab-item v-for="item in items" :key="item.tab">
                        <div class="iframe-container">
                            <iframe :src="`${item.content}`" width="300" height="380" frameborder="0" allowtransparency="true" allow="encrypted-media"></iframe>
                        </div>
                    </v-tab-item>
                </v-tabs-items>
            </v-container>
        </section>
    </div>
</template>

<script>
export default {
    data() {
        return {
            tab: null,
            items: [
                { tab: 'Cyber Punk', content: 'https://open.spotify.com/embed/playlist/4cfChdML5Kv9bylf6eNyt0' },
                { tab: 'Dark Electro', content: 'https://open.spotify.com/embed/playlist/5arKLuU39VKym4leePpdpA' }
            ],
        }
    },
}
</script>

<style scoped>
.iframe-container {
    position: relative;
    overflow: hidden;
    padding-top: 96.25%;
}

.iframe-container iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border: 0;
}
</style>