<template>
  <div>
    <Navigation :color="color" :flat="flat" />
    <v-main class="pt-0">
      <Home />
      <Skill />
      <About />
      <Project />
      <Contact />
    </v-main>
    <v-scale-transition>
      <v-btn
        fab
        v-show="fab"
        v-scroll="scroll"
        dark
        fixed
        bottom
        right
        color="primary"
        @click="toTop"
      >
        <v-icon> mdi-arrow-up </v-icon>
      </v-btn>
    </v-scale-transition>
    <Footer />
  </div>
</template>

<script>
import Navigation from "~/components/Navigation";
import Home from "~/pages/home";
import About from "~/pages/about";
import Contact from "~/pages/contact";
import Skill from "~/pages/skill";
import Project from "~/pages/project";
import Footer from "~/components/Footer";

export default {
  components: {
    Navigation,
    Home,
    About,
    Contact,
    Skill,
    Project,
    Footer,
  },
  data: () => ({
    color: "",
    flat: null,
    fab: null,
  }),
  watch: {
    fab(val) {
      if (val) {
        this.color = "primary";
        this.flat = false;
      } else {
        this.color = "transparent";
        this.flat = true;
      }
    },
  },
  created() {
    if (process.client) {
      const top = window.pageYOffset || 0;
      if (top <= 60) {
        this.color = "transparent";
        this.flat = true;
      }
    }
  },
  methods: {
    scroll(e) {
      if (process.client) {
        if (typeof window === "undefined") return;
        const top = window.pageYOffset || e.target.scrollTop || 0;
        this.fab = top > 60;
      }
    },
    toTop() {
      this.$vuetify.goTo(0);
    },
  },
};
</script>

<style scoped>
</style>
