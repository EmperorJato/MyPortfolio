<template>
  <div>
    <v-navigation-drawer
      v-model="drawer"
      app
      temporary
      dark
      src="img/drawer_bg.jpg"
    >
      <v-list>
        <v-list-item
          >s
          <v-list-item-avatar>
            <img src="img/logo_white.png" alt="Logo" />
          </v-list-item-avatar>
          <v-list-item-content>
            <v-list-item-title class="title"> Emperor Jato </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>

      <v-divider />

      <v-list>
        <v-list-item
          v-for="([icon, text, link], i) in items"
          :key="i"
          link
          @click="$vuetify.goTo(link)"
        >
          <v-list-item-icon>
            <v-icon>{{ icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title class="subtitle-1">
              {{ text }}
            </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      app
      :color="color"
      :flat="flat"
      dark
      class="px-15"
      :class="{ expand: flat }"
    >
      <v-toolbar-title>
        <v-img src="img/logo_white.png" max-width="50px" />
      </v-toolbar-title>
      <v-spacer />
      <v-app-bar-nav-icon
        @click.stop="drawer = !drawer"
        class="mr-4"
        v-if="isXs"
      />
      <div v-else>
        <v-btn text @click="$vuetify.goTo('#home')">
          <span class="mr-2 home">Home</span>
        </v-btn>
        <v-btn text @click="$vuetify.goTo('#skill')">
          <span class="mr-2 skill">Skills</span>
        </v-btn>
         <v-btn text @click="$vuetify.goTo('#about')">
          <span class="mr-2 about">About</span>
        </v-btn>
        <v-btn text @click="$vuetify.goTo('#project')">
          <span class="mr-2 project">Projects</span>
        </v-btn>
        <v-btn text @click="$vuetify.goTo('#contact')">
          <span class="mr-2 contact">Contact</span>
        </v-btn>
      </div>
    </v-app-bar>
  </div>
</template>

<script>
export default {
  props: {
    color: String,
    flat: Boolean,
  },
  data: () => ({
    drawer: null,
    isXs: false,
    items: [
      ["mdi-home", "Home", "#home"],
      ["mdi-head-cog", "Skills", "#skills"],
      ["mdi-folder", "Projects", "#projects"],
      ["mdi-account-details", "About", "#about"],
      ["mdi-card-account-mail", "Contact", "#contact"],
    ]
  }),
  watch: {
    isXs(val) {
      if (!val) {
        if (this.drawer) {
          this.drawer = false;
        }
      }
    },
  },
  methods: {
    onResize() {
      if (process.client) {
        this.isXs = window.innerWidth < 850;
      }
    },
    // activeBar() {
    //   if (process.client) {
    //     window.addEventListener("scroll", (event) => {
    //       const navButton = this.$el.querySelectorAll(".nav-links");
    //       const fromTop = window.scrollY;
    //       navButton.forEach((link) => {
    //         console.log(link)
    //         let section = this.$el.querySelector(link.hash);
            
    //         if (
    //           section.offsetTop <= fromTop &&
    //           section.offsetTop + section.offsetHeight > fromTop
    //         ) {
    //           link.classList.add("active");
    //         } else {
    //           link.classList.remove("active");
    //         }
           
    //       });
    //     });
    //   }
    // },
  },
  mounted() {
    this.onResize();
    window.addEventListener("resize", this.onResize, { passive: true });
  },
};
</script>

<style scoped>
.v-toolbar {
  transition: 0.6s;
}

.expand {
  height: 80px !important;
  padding-top: 10px;
}

</style>