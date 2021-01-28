<template>
  <v-app>
    <v-navigation-drawer
      v-model="nav"
      app
      absolute
      temporary
      dark
    ></v-navigation-drawer>

    <!-- комментарий -->

    <v-content class="px-12 py-3" app>
      <v-container fluid>
        <router-view/>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  components: {
  },

  data: () => ({
    nav: false
  }),
};
</script>
