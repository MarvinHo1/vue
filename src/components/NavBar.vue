<template>
  <v-container fluid grid-list-md>
    <v-app-bar dark >
      <v-icon large color="grey" >mdi-alpha-k-box-outline</v-icon>
      <v-icon large color="grey" >mdi-shield-outline</v-icon>
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-spacer></v-spacer>

      <v-icon 
        medium color="grey" class="pa-8" >mdi-bell-alert-outline</v-icon>
      <v-icon medium color="grey" class="pa-2" >mdi-clipboard-arrow-right-outline</v-icon>
    </v-app-bar>
  </v-container>
</template>

<script>
  export default {
    name: 'NavBar',

    data: () => ({
      //
    }),
  }
</script>
