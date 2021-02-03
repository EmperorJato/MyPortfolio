<template>
  <section id="home">
    <v-parallax dark src="img/home_bg.jpg" height="750">
      <v-row align="center" justify="center">
        <v-col cols="10">
          <v-row align="center" justify="center">
            <v-col cols="12" md="6" xl="8">
              <h1 class="display-2 font-weight-bold mb-4">My Portfolio</h1>
              <h1 class="font-weight-light">
                Hello, I'm
                <div class="d-inline font-weight-medium">Steto Javellana</div>
                a
                <div>Full Stack Web Developer</div>
              </h1>
              <v-btn
                rounded
                outlined
                large
                dark
                class="mt-5"
                @click="$vuetify.goTo('#skill')"
              >
                Getting Started
                <v-icon class="ml-2"> mdi-arrow-down </v-icon>
              </v-btn>
            </v-col>
            <v-col cols="12" md="6" xl="4" class="hidden-sm-and-down"> </v-col>
          </v-row>
        </v-col>
      </v-row>
      <!-- <div class="svg-border-waves text-white">
        <v-img src="img/borderWaves.svg" />
      </div> -->
    </v-parallax>
  </section>
</template>

<script>
export default {
  head() {
    return {
      title: "Home",
    };
  },
};
</script>

<style scoped>
section {
  position: relative;
}

.svg-border-waves .v-image {
  position: absolute;
  bottom: 0;
  left: 0;
  height: 3rem;
  width: 100%;
  overflow: hidden;
}
</style>