<template>
  <v-footer
      v-if="page === 0"
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
</template>

<script>
export default {
  name: "Footer",
  props: ['page']
}
</script>

<style scoped>

</style>
