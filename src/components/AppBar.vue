<template>
    <div>
        <v-app-bar>
            <v-app-bar-nav-icon @click="toggleDrawer('drawer')" />
            <v-spacer/>
            <v-btn
            @click="signIn"
            text
            >Sign In</v-btn>
            <v-btn
            @click="signOut"
            text
            >Sign Out</v-btn>
        </v-app-bar>
    </div>
</template>

<script>
import { mapActions } from 'vuex'

export default {
    methods: {
        ...mapActions({
            toggleDrawer: "auth/toggle_drawer", //also supports payload `this.nameOfAction(amount)` 
            signIn: "auth/sign_in",
            signOut: "auth/sign_out"
    })
    },
}
</script>

<style lang="scss" scoped>

</style>