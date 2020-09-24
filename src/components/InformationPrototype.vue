<template>
  <v-container fluid class="my-5">
    <p>{{select}}</p>
    <!-- <TabInformation></TabInformation> -->
    <v-layout class= "pl-8" row wrap>
      <v-flex><div class="caption grey--text"> USDOT </div></v-flex>
      <v-flex><div class="caption grey--text"> Carrier Code </div></v-flex>
      <v-flex><div class="caption grey--text"> Carrier Name </div></v-flex>
      <v-flex><div class="caption grey--text"> Email Address </div></v-flex>
      <v-flex><div class="caption grey--text"> Requested At </div></v-flex>
      <v-flex><div class="caption grey--text"> Invite </div></v-flex>
      <v-flex><div class="caption grey--text"> Invited </div></v-flex>
      <v-flex><div class="caption grey--text"> Action </div></v-flex>
    </v-layout>
      <v-card
      v-for="infos in info"
      :key="infos.usdot"
      row
      class="ma-1 text-center justify-center"
      >
      <v-layout row wrap>
        <v-flex> 
          {{infos.usdot}}
        </v-flex>
        <v-flex> 
          {{infos.carrierCode}}
        </v-flex>
        <v-flex> 
          {{infos.carrierName}}
        </v-flex>
        <v-flex> 
          {{infos.emailAddress}} 
        </v-flex>
        <v-flex> 
          {{infos.requestedAt}}  
        </v-flex>
        <v-flex> 
          <v-btn 
          small 
          > 
            {{infos.invite}}
          </v-btn>
        </v-flex>
        <v-flex> 
            {{infos.invited}}
        </v-flex>
        <v-flex> 
          <v-icon 
          medium color="grey" 
          class="pa-2"
          >
            {{infos.action}}
          </v-icon>
        </v-flex>
      </v-layout>
    </v-card>
  </v-container>
</template>


<script>


export default {
  props: ['select'],
  name: 'Information2',

  data: () => ({
    info: null,
  }),

  methods: {
    //
  },

  created() {
    let data = this.select.filter(request => {return request.tab === "Select Request"});
    this.info = data[0].data
  }
}
</script>