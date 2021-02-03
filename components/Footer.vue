<template>
  <v-footer dark padless>
    <v-card flat tile class="primary white--text text-center">
      <v-card-text>
        <v-btn
          v-for="(icon, i) in icons"
          :key="i"
          class="mx-4 white--text"
          :href="icon.link"
          target="_blank"
          icon
        >
          <v-icon size="24px">{{ icon.text }}</v-icon>
        </v-btn>
      </v-card-text>
      <v-card-text class="white--text">
         <strong>&#169; Steto Javellana</strong> - {{ new Date().getFullYear() }}
      </v-card-text>
    </v-card>
  </v-footer>
</template>

<script>
export default {
  data: () => ({
    icons: [
      { text: "mdi-facebook", link: "" },
      { text: "mdi-twitter", link: "" },
      { text: "mdi-google", link: "" },
    ],
  }),
};
</script>

<style scoped>
.v-card {
  width: 100%;
}
</style>