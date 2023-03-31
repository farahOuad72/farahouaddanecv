<template>
  <v-card
      class="mx-auto my-12"
  >
    <div class="card-headers">
      <h2 class="about-me">Contact</h2>
    </div>
    <div class="container">
      <v-row >
          <div class="box">
            <v-row>
              <v-col cols="2" align-self="center">
                <v-icon class="icon-contact" icon="mdi-linkedin">mdi-linkedin</v-icon>
              </v-col>
              <v-col cols="10" align-self="center">
                <h4> Linkedin </h4>
                <a href="https://www.linkedin.com/in/farah-ouaddane/" target="_blank">Check my professional experience.</a>
              </v-col>
              <v-col cols="2" align-self="center">
                <v-icon class="icon-contact" icon="mdi-phone">mdi-phone</v-icon>
              </v-col>
              <v-col cols="10">
                <h4> Phone </h4>
                <a href="tel:" target="_blank">+33752991004</a>
              </v-col>
              <v-col cols="2" align-self="center">
                <v-icon class="icon-contact" icon="mdi-email">mdi-email</v-icon>
              </v-col>
              <v-col cols="10">
                <h4> Email </h4>
                <a href="mailto:" target="_blank">farah.ouaddane@uha.fr</a>
              </v-col>
            </v-row>
          </div>
      </v-row>
    </div>


  </v-card>
</template>

<script>
export default {
  name: "AboutMe",
  methods: {

  },

}
</script>

<style scoped>
.container {
  width: 50%;
  margin: 0 auto;
  padding: 2rem;
}
.container-small {
  width: 100%;
  margin: 0 auto;
  padding: 2rem;
}
.box {
  height: fit-content;
  width: 100%;
  border: 2px solid var(--third-color);
  box-shadow: 4px 4px 0 var(--third-color);
  padding: 20px;
}
.box:nth-child(odd) {
  transform: skew(-10deg);
}
.box:nth-child(even) {
  transform: skew(10deg);
}
a {
  text-decoration: none;
  color: var(--primary-color) !important;
}
.icon-contact{
  font-size: 35px;
}

</style>