<template>
  <v-col align="center" class="foreground">
    <h1 class="indigo--text" style="text-align: center">{{ text }}</h1>
    <v-btn @click="changePage(1)" color="indigo" dark class="align-center mt-5" x-large>Start</v-btn>
  </v-col>
</template>

<script>
export default {
  name: "Welcome",
  props: ['text', 'changePage'],
  methods: {

  }
}
</script>


</style>
