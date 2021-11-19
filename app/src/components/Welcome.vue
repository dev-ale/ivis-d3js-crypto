<template>
  <v-col align="center">
    <h1 class="indigo--text" style="text-align: center">{{ text }}</h1>
    <v-btn @click="startFunction" color="indigo" dark class="align-center mt-5" x-large>Start</v-btn>
  </v-col>


</template>

<script>
export default {
  name: "Welcome",
  props: ['text', 'startFunction'],
  methods: {

  }
}
</script>

<style scoped>

</style>
