<template>
  <v-container>
    <v-row
        no-gutters
        v-for="n in 3"
        :key="n"
        class="px-5">

      <v-col
          v-for="m in 3"
          :key="m"
          cols="12"
          sm="4"
          class="px-5"
      >
        <v-hover v-slot="{ hover }">
          <v-card
              @click="change(n*m)"
              width="400"
              height="250"
              class="rounded-xl "

              :elevation="hover ? 16 : 2"
          >
            <v-row justify="center" align-content="center" class="mt-5">
              <v-col>
                <p align="center"><strong>{{ (n*m) }} - Chart</strong></p>
              </v-col>
            </v-row>
          </v-card>
        </v-hover>

      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import ChartOne from "./ChartOne";
export default {
name: "Overview",
  props: ['changePage'],
  components: {ChartOne},
  methods: {
    change(page) {
      this.changePage(page);
    }
  }
}
</script>

<style scoped>

</style>
