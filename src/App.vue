<template>
  <v-app>
    <v-container fluid grid-list-md>
      <v-app-bar dark >
        <v-icon large color="grey" >mdi-alpha-k-box-outline</v-icon>
        <v-icon large color="grey" >mdi-shield-outline</v-icon>

        <v-spacer></v-spacer>

      <v-tabs grow>
        <v-tab to="/">Home</v-tab>
        <v-tab to="/about">About</v-tab>
        <v-tab to="/information" >Information</v-tab>
      </v-tabs>

      <v-spacer></v-spacer>

        <v-icon class="pa-8" medium color="grey" >mdi-bell-alert-outline</v-icon>
        <v-icon class="pa-2" medium color="grey" >mdi-clipboard-arrow-right-outline</v-icon>
      </v-app-bar>
      <router-view></router-view>
    </v-container>
  </v-app>
</template>

<style lang="scss">
//
</style>
