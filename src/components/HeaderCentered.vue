<template>
    <div>
        <v-sheet :height="$vuetify.breakpoint.xsOnly ? '100vh' : '80vh'">
            <v-container class="fill-height" fluid>
                <v-row class="fill-height" fluid align="center" justify="center">
                    <v-col cols="12" sm="8" md="4" class="text-center">
                        <h1 class="font-weight-thin  mx-auto">
                            My awesome title
                        </h1>
                        <v-btn large class="mt-4 white--text" color="primary" href="" target="_blank">
                            Call to action
                        </v-btn>
                    </v-col>
                </v-row>
            </v-container>
        </v-sheet>
    </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>

</style>