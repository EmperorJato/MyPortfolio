<template>
  <section id="project" class="my-16">
    <v-container fluid>
      <v-row align="center" justify="center">
        <v-col cols="10">
          <v-card>
            <h1 class="text-center pt-6 font-weight-light display-1">
              Projects
            </h1>
            <v-divider class="my-6"></v-divider>
            <v-row class="text-center" justify="center" align="center">
              <v-col class="col-12 col-sm-6 col-md-4">
                <v-card-text justify="center" align="center">
                  <v-img
                    src="img/purchasing.svg"
                    max-height="200"
                    max-width="200"
                  ></v-img>
                  <div class="text--disabled text-uppercase text-h5 my-2">
                    Purchase Requisition
                  </div>
                  <v-btn
                   
                    rounded
                    outlined
                    color="primary"
                    class="mt-6"
                  >
                    <v-icon left> mdi-eye </v-icon>
                    View
                  </v-btn>
                </v-card-text>
              </v-col>
              <v-divider
                vertical
                class="my-6 mr-n8"
                v-if="this.$vuetify.breakpoint.mdAndUp"
              ></v-divider>
              <v-divider
                class="mx-12"
                v-if="!this.$vuetify.breakpoint.smAndUp"
              ></v-divider>
              <v-col class="col-12 col-sm-6 col-md-4">
                <v-card-text justify="center" align="center">
                  <v-img
                    src="img/blogging.svg"
                    max-height="200"
                    max-width="200"
                    class="mt-3"
                  ></v-img>
                  <div class="text--disabled text-uppercase text-h5 mt-2 mb-2">
                    Blogging System
                  </div>
                  <v-btn
                  
                    rounded
                    outlined
                    color="primary"
                    class="mt-6"
                  >
                    <v-icon left> mdi-eye </v-icon>
                    View
                  </v-btn>
                </v-card-text>
              </v-col>
            </v-row>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </section>
</template>

<script>
export default {
  name: "Project",
};
</script>

<style scoped>
</style>
