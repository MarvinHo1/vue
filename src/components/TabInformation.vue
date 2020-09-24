<template>
  <v-container fluid >
    <v-app-bar dark >
      <v-tabs>
        <v-tab
          v-for="selection in select" 
          :key="selection.key"
          ref='selected'
          value="`${selectedTab}`"
          @click="selectedTab"
          >
          {{selection.tab}}
        </v-tab>
      </v-tabs>
    </v-app-bar>
    <Information v-bind:select=select ></Information>
  </v-container>
</template>

<script>
import Information from './Information.vue'

export default {
  name: 'TabInformation',
  components: {
    Information
  },
  data: () => ({
    tab: '',
    select: [
      {
        tab: "Select Request", 
        key: "1",
        data: [
          {
            Usdot: "1203948", 
            Carrier_Code: "SWIFTC",
            Carrier_Name: "Billy Bobby",
            Email_Address: "example@email.address.com",
            Requested_At: "02/20/20",
            Invite: "Invite",
            Invited: "", 
            Action: "mdi-clipboard-multiple-outline",
          },
          {
            Usdot: "1503948", 
            Carrier_Code: "",
            Carrier_Name: "John Wayne",
            Email_Address: "example@email.address.com",
            Requested_At: "04/24/04",
            Invite: "Invite",
            Invited: "kinda", 
            Action: "mdi-clipboard-multiple-outline"
          }
        ]
      },
      {
        tab: "Select User", 
        key: "2"
      },
      {
        tab: "Approved Loads", 
        key: "3"
      },
      {
        tab: "History", 
        key: "4"
      },
      {
        tab: "Event", 
        key: "5"
      },
    ],
  }),
  methods: {
    selectedTab: function(event) {
      this.tab=event.target.innerText
      console.log(event.target.innerText, typeof this.tab, 'hello')
    }
  },
}
</script>

<style lang="scss">
  .v-slide-group__wrapper {
    width: 10px;
}
</style>