<template>
  <v-app>
    <Appbar :page="showView" :change-page="changeView"/>
    <v-main>
      <vue-particles class="background" color="#3f51b5"></vue-particles>
      <v-container fill-height class="foreground">
        <v-row class="justify-center align-center">
          <v-col cols="12" sm="12" xl="12">

            <Welcome v-if="showView === 0" text="crypto stats" :change-page="changeView"/>

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
    <Footer :page="showView"/>
  </v-app>
</template>

<script>
import Welcome from "./components/Welcome";
import ChartOne from "./components/ChartOne";
import Overview from "./components/Overview";
import Appbar from "./components/Appbar";
import Footer from "./components/Footer";

export default {
  name: 'App',

  components: {
    Footer,
    Appbar,
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

<style scoped>
.background {
  position : absolute;
  width:100%;
  height:100%;
}

.foreground {
  z-index:2;
}
</style>
