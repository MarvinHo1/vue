<template>
  <v-card >
    <v-card-title class="primary" row>
      <h2>{{company}} Expirations</h2>
      <v-spacer></v-spacer>
      <v-icon>mdi-close</v-icon>
    </v-card-title>
    <v-data-table
    :headers="headers"
    :items="info"
    hide-default-footer
    >
    </v-data-table>

  </v-card>
</template>

<script>
  export default {
    name: 'CarrierPopup',

    data: () => ({
      company: "SwiftCarrier",
      requests: [
        {Code: "ALIA", Priority: 2, Description: 'Reefer Stuff for 55k', Start_date: "05/23/08", Created: "05/22/08"},
        {Code: "BELL", Priority: 1, Description: 'Prem items 1.5 million', Start_date: "08/23/08", Created: "04/22/08"},
        {Code: "ROLL", Priority: 6, Description: 'Cargo replacement 200k', Start_date: "12/23/08", Created: "03/22/08"},
        {Code: "SHOO", Priority: 5, Description: 'Random Misc for 350k', Start_date: "06/23/08", Created: "02/22/08"},
        {Code: "BAMS", Priority: 1, Description: 'Nice relaxing drive priceless', Start_date: "01/23/08", Created: "11/22/08"},
      ],
      headers: [
        {
          text: 'Code',
          align: 'start',
          sortable: false,
          value: 'Code',
        },
        { text: 'Priority', value: 'Priority' },
        { text: 'Description', value: 'Description' },
        { text: 'Start_date', value: 'Start_date' },
        { text: 'Created', value: 'Created' },
      ],
      info: [
        {
          Code: 'ALIA',
          Priority: 2,
          Description: 'Reefer Stuff for 55k',
          Start_date: "05/23/08",
          Created: "05/22/08",
        },
        {Code: "BELL", Priority: 1, Description: 'Prem items 1.5 million', Start_date: "08/23/08", Created: "04/22/08"},
        {Code: "ROLL", Priority: 6, Description: 'Cargo replacement 200k', Start_date: "12/23/08", Created: "03/22/08"},
        {Code: "SHOO", Priority: 5, Description: 'Random Misc for 350k', Start_date: "06/23/08", Created: "02/22/08"},
        {Code: "BAMS", Priority: 1, Description: 'Nice relaxing drive priceless', Start_date: "01/23/08", Created: "11/22/08"},
      ],
    }),
  }
</script>