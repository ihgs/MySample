<template>
  <v-app>
    <!-- <v-app-bar
      app
      color="primary"
      dark
    >
    </v-app-bar> -->

    <v-main>
      <MyTable/>
    </v-main>
  </v-app>
</template>

<script>
import MyTable from './components/MyTable.vue';

export default {
  name: 'App',

  components: {
    MyTable,
  },

  data: () => ({
    //
  }),
};
</script>
