<template>
  <section class="pb-8 my-16" id="contact">
    <v-container fluid>
      <v-row align="center" justify="center">
        <v-col cols="10">
          <v-row justify="center">
            <v-col cols="12" sm="5">
              <h1 class="font-weight-light display-1">Contact</h1>
              <h3 class="font-weight-light mt-3">
                Let's talk about everything.<br />Please feel free to contact me if
                you are interested in hiring me..
              </h3>
              <h3 class="font-weight-light mt-3">
                Phone Number: +639275371519
              </h3>
              <h3 class="font-weight-light mt-3">
                Email: stetojavellana9@gmail.com
              </h3>
            </v-col>
            <v-col cols="12" sm="7">
              <v-form
                @submit.prevent="submit"
                ref="form"
                v-model="valid"
                lazy-validation
                aria-autocomplete="off"
              >
                <v-text-field
                  outlined
                  label="Name"
                  required
                  :rules="rules.name"
                  prepend-inner-icon="mdi-account"
                >
                </v-text-field>

                <v-text-field
                  outlined
                  label="Email"
                  required
                  type="email"
                  :rules="rules.email"
                  prepend-inner-icon="mdi-email"
                  background-color="none"
                >
                </v-text-field>

                <v-textarea
                  outlined
                  label="Message"
                  required
                  rows="4"
                  row-height="30"
                  :rules="rules.message"
                  prepend-inner-icon="mdi-comment-text"
                >
                </v-textarea>
                <v-btn
                  :disabled="!valid"
                  color="primary"
                  rounded
                  block
                  type="submit"
                >
                  <v-icon left> mdi-send </v-icon>
                  Send Message
                </v-btn>
              </v-form>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
    <div class="svg-border-waves text-white">
      <v-img src="img/borderWavesBlue.svg" />
    </div>
  </section>
</template>

<script>
export default {
  data: () => ({
    valid: true,
    form: {
      name: "",
      email: "",
      message: "",
    },
    rules: {
      name: [(v) => !!v || "Name is required"],
      email: [
        (v) => !!v || "Email is required",
        (v) => /.+@.+\..+/.test(v) || "E-mail must be valid",
      ],
      message: [
        (v) => !!v || "Message is required",
        (v) =>
          (v && v.length >= 10) || "Message must be greater than 10 characters",
      ],
    },
  }),

  methods: {
    submit() {
      this.$refs.form.validate();
    },
  },
};
</script>

<style scoped>
.svg-border-waves .v-image {
  position: absolute;
  bottom: 0;
  left: 0;
  height: 3rem;
  width: 100%;
  overflow: hidden;
}

</style>