<template>
  <section id="skill" class="pb-8 my-16">
    <v-container fluid>
      <v-row align="center" justify="center">
        <v-col cols="10">
          <v-card>
            <h1 class="text-center pt-6 font-weight-light display-1">Skills</h1>
            <v-divider class="my-6"></v-divider>
            <v-row class="text-center">
              <v-col
                cols="12"
                xsm="12"
                sm="6"
                md="4"
                v-for="(skill, i) in skills"
                :key="i"
              >
                <v-hover v-slot:default="{ hover }" open-delay="200">
                  <v-card :elevation="hover ? 16 : 2" class="mx-6 mb-3" outlined>
                    <v-list-item three-line>
                      <v-list-item-content>
                        <v-list-item-title class="headline mb-1 text-left">
                          {{ skill.name }}
                        </v-list-item-title>
                      </v-list-item-content>
                      <v-list-item-avatar tile size="100">
                        <div class="flex-center">
                              <v-img :src="skill.svg" max-width="70px" ></v-img>
                        </div>
                      </v-list-item-avatar>
                    </v-list-item>
                  </v-card>
                </v-hover>
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
  data: () => ({
    skills: [
      { svg: "img/html5.svg", name: "HTML5" },
      { svg: "img/css-3.svg", name: "CSS3" },
      { svg: "img/javascript.svg", name: "JAVASCRIPT" },
      { svg: "img/vue.svg", name: "VUE" },
      { svg: "img/vuetify.svg", name: "VUETIFY" },
      { svg: "img/nuxt.svg", name: "NUXT" },
      { svg: "img/php.svg", name: "PHP" },
      { svg: "img/laravel.svg", name: "LARAVEL" },
      { svg: "img/mysql.svg", name: "MYSQL" },
    ],
  }),
};
</script>

<style scoped>
.circle-1 {
  border-radius: 50%;
  width: 90px;
  height: 90px;
  background-color: #f0f8ff;
  display: flex;
  align-items: center;
  justify-content: center;
}

.circle-2 {
  border-radius: 50%;
  width: 70px;
  height: 70px;
  background-color: #e0effc;
  display: flex;
  align-items: center;
  justify-content: center;
}

.flex-center {
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>