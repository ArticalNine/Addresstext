<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
       <v-app-bar-nav-icon @click.stop="toggleSideMenu"></v-app-bar-nav-icon>
      <v-toolbar-title>マイアドレス帳</v-toolbar-title>
      <v-spacer></v-spacer>

      <v-btn
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
        text
      >
        <span class="mr-2">Latest Release</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>
     <SideNav/>
 <v-container fluid fill-height align-start>
        <router-view/>
      </v-container>


   
  </v-app>
</template>

<script>

import SideNav from './components/SideNav'
import { mapActions } from 'vuex'
export default {
  name: 'App',
  components: {
    SideNav
  },
  data: () => ({
    //
  }),
    methods: {
      openSideMenu () {
      this.$store.dispatch('toggleSideMenu')
    },
    ...mapActions(['toggleSideMenu'])
  }
};
</script>
