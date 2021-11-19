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
  </v-col>

</template>

<script>
export default {
  name: "ChartOne",
  props: ['title',],
}
</script>

<style scoped>

</style>
