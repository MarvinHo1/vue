<template>
  <v-contaier>
    <!-- <p>{{select}}</p> -->
    <v-layout center row class="mb-4 mt-9" align-items>
      <v-flex class="headline font-weight-medium">Pending Selected Requests</v-flex>
      <v-btn medium class="primary">Invite Carrier</v-btn>
    </v-layout>
    <v-data-table
      :headers="headers"
      :items="info"
      disable-sort
      :items-per-page="5"
    >
      <template v-slot:item="row" >
        <tr>
          <td>{{row.item.Usdot}}</td>
          <td>
            <v-dialog max-width="55%" >
              <template v-slot:activator="{ on, attrs }" >
                <v-btn
                small
                v-bind="attrs"
                v-on="on"
                class="primary"
                v-if="row.item.Carrier_Code.length >= 3 "
                >
                  {{row.item.Carrier_Code}}
                </v-btn>
                <div
                v-else
                >
                  NOT SET UP
                </div>
              </template>
              <CarrierPopup></CarrierPopup>
            </v-dialog>
          </td>
          <td>{{row.item.Carrier_Name}}</td>
          <td>{{row.item.Email_Address}}</td>
          <td>{{row.item.Requested_At}}</td>
          <td>
            <v-btn 
            small
            class="primary"
            >
              {{row.item.Invite}}
            </v-btn>
          </td>
          <td>{{row.item.Invited}}</td>
          <td>
            <v-icon 
            medium color="grey" 
            class="pa-2"
            >
            {{row.item.Action}}
            </v-icon>
          </td>
        </tr>
      </template>
    </v-data-table>
  </v-contaier>
</template>


<script>
import CarrierPopup from "./CarrierPopup.vue"

export default {
  props: ['select'],
  name: 'Information',
  components: {
    CarrierPopup
  },

  data: () => ({
    info: null,
    headers: null,
  }),

  methods: {
    //
  },

  created() {
    let headersArr = [];
    let infoArr = []
    let data = this.select.filter(request => {return request.tab === "Select Request"});
    let headerTitles = Object.keys(data[0].data[0]);
    
    data[0].data.filter(value => {
      infoArr.push(value)
    })

    for (let i = 0; i < headerTitles.length; i++) {
      let formatHeaders = headerTitles[i].replace(/[^a-zA-Z ]/, ' ')
      headersArr.push({
        text: formatHeaders,
        value: headerTitles[i],
        })
    }

    this.headers = headersArr;
    this.info = infoArr;
  }
}
</script>