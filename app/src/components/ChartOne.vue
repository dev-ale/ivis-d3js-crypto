<template>
  <v-col align="center" sm="12">
    <h2>{{ title }}</h2>
    <v-card :height="this.$vuetify.breakpoint.height * 0.7" :width="this.$vuetify.breakpoint.width * 0.8" class="rounded-xl" elevation="5">
      <v-row justify="center" align-content="center" class="mt-5">
        <v-col>
          <p align="center"><strong>BTC</strong></p>
        </v-col>
      </v-row>
    </v-card>
    <v-pagination
        class="mt-5"
        color="indigo"
        v-model="actualPage"
        :length="8"
        circle
        @input="change"
    ></v-pagination>
  </v-col>

</template>

<script>
export default {
  name: "ChartOne",
  props: ['title','page','changePage'],
  data: () => ({
    actualPage: 1
  }),
  methods: {
    change() {
      this.changePage(this.actualPage);
    }
  }
}
</script>

<style scoped>

</style>
