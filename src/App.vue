<template>
  <v-app>
    <AppBar/>
    <NavDrawer/>
    <v-content>
      <router-view />
    </v-content>
  </v-app>
</template>

<script>
import NavDrawer from '@/components/NavDrawer';
import AppBar from '@/components/AppBar';

export default {
  name: 'App',

  components: {
    NavDrawer,
    AppBar
  },

  data: () => ({
    //
  }),
};
</script>
