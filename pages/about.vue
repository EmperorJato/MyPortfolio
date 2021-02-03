<template>
  <section id="about" class="my-16">
    <v-container fluid>
      <v-row align="center" justify="center" style="background: none;">
        <v-col cols="10">
          <v-row align="center" justify="center">
            <v-col cols="12" md="5" class="d-none d-md-flex">
              <v-img
                src="img/about.svg"
                class="d-block ml-auto mr-auto"
              />
            </v-col>
            <v-col cols="12" md="7">
              <h1 class="font-weight-light display-1 mb-3 text-right">
                About Me
              </h1>
              <v-row>
                <v-col cols="12" class="d-flex align-center">
                  <h1 class="font-weight-light text-justify">
                    Hi, I am Steto Javellana, I have been a full stack web
                    developer for 6 months.
                  </h1>
                </v-col>
              </v-row>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
  </section>
</template>

<script>
export default {
  head() {
    return {
    };
  }
};
</script>

<style scoped>
</style>