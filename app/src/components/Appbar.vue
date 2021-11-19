<template>
  <v-app-bar v-if="page > 0" flat absolute color="transparent">
    <v-btn
        @click="changePage(0)"
        text
    >
      <v-icon size="40" color="indigo">mdi-home</v-icon>
      <span class="ml-2 indigo--text">Home</span>
    </v-btn>
    <v-spacer/>
    <v-btn
        v-if="page < 10"
        @click="changePage(10)"
        text
    >
      <span class="mr-2 indigo--text">Overview</span>
      <v-icon size="40" color="indigo">mdi-view-dashboard</v-icon>

    </v-btn>
  </v-app-bar>
</template>

<script>
export default {
  name: "Appbar",
  props: ['page','changePage']
}
</script>

<style scoped>

</style>
