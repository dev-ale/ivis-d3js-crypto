<template>
  <v-app>


    <v-app-bar v-if="showView > 0" flat absolute color="transparent">
      <v-btn
          @click="showView = 0"
          text
      >
        <v-icon size="40" color="indigo">mdi-home</v-icon>
        <span class="ml-2 indigo--text">Home</span>
      </v-btn>
      <v-spacer/>
      <v-btn
          v-if="showView < 10"
          @click="showView = 10"
          icon
      >
        <v-icon size="40" color="indigo">mdi-view-dashboard</v-icon>

      </v-btn>
    </v-app-bar>


    <v-main>
      <v-container fill-height>
        <v-row class="justify-center align-center">
          <v-col cols="12" sm="12" xl="12">

            <Welcome v-if="showView === 0" text="crypto stats" :start-function="startFunction"/>

            <ChartOne v-if="showView === 1" title="1 - Overview" :page="showView" :change-page="changeView"/>

            <ChartOne v-if="showView === 2" title="2 - Weekdays" :page="showView" :change-page="changeView"/>

            <ChartOne v-if="showView === 3" title="3 - Dominance" :page="showView" :change-page="changeView"/>

            <ChartOne v-if="showView === 4" title="4 - Google Trend" :page="showView" :change-page="changeView"/>

            <ChartOne v-if="showView === 5" title="5 - Youtube Trend" :page="showView" :change-page="changeView"/>

            <ChartOne v-if="showView === 6" title="6 - Twitter Trend" :page="showView" :change-page="changeView"/>

            <ChartOne v-if="showView === 7" title="7 - BTC - ETH" :page="showView" :change-page="changeView"/>

            <ChartOne v-if="showView === 8" title="8 - Countries" :page="showView" :change-page="changeView"/>

            <ChartOne v-if="showView === 9" title="9 - ???" :page="showView" :change-page="changeView"/>

            <Overview v-if="showView === 10" :change-page="changeView"/>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
    <v-footer
        v-if="showView === 0"
        color="transparent"
        padless
    >
      <v-row
          justify="center"
          no-gutters
      >
        <v-btn
            href="https://github.com/dev-ale/ivis-d3js-crypto"
            target="_blank"
            color="indigo"
            text
            rounded
            class="my-2"
        >
          <v-icon size="40">mdi-github</v-icon>

        </v-btn>
        <v-col
            class="indigo--text py-4 text-center white--text"
            cols="12"
        >
          {{ new Date().getFullYear() }} — <strong>Alejandro Garcia</strong>
        </v-col>
      </v-row>
    </v-footer>
  </v-app>
</template>

<script>


import Welcome from "./components/Welcome";
import ChartOne from "./components/ChartOne";
import Overview from "./components/Overview";
export default {
  name: 'App',

  components: {
    Overview,
    ChartOne,
    Welcome

  },
  methods: {
    startFunction() {
      this.changeView(1);
    },
    changeView(pageNumber) {
      this.showView = pageNumber;
    }
  },

  data: () => ({
    showView: 0
  }),
};
</script>
