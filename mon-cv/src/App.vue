<template>
  <v-app>
    <myToolbar ref="toolbar"/>
    <v-main>
      <div id="main-view">
        <about ref="about-me" />
        <experiences ref="experience" />
        <studies ref="education" />
        <stack ref="stack" />
        <hobbies ref="hobbies" />
        <contact ref="contact" />
      </div>

    </v-main>
    <v-btn
        v-if="showButton"
        color="var(--third-color)"
        fab
        bottom
        right
        fixed
        @click="scrollTop"
    >
      <v-icon>mdi-arrow-up</v-icon>
    </v-btn>
  </v-app>

</template>

<script>
import myToolbar from "@/components/MyToolbar";
import about from "@/components/AboutMe";
import studies from "@/components/MyStudies";
import experiences from "@/components/MyExperiences";
import stack from "@/components/MyStack";
import hobbies from "@/components/MyHobbies";
import contact from "@/components/ContactMe";
import "./assets/css/general.css";
import "./assets/css/variables.css";
export default {
  name: "app",
  components: { myToolbar, about, studies, experiences, hobbies, contact, stack },
  data() {
    return {
      showButton: false
    };
  },
  methods: {
    scrollTop() {
      window.scrollTo({ top: 0, behavior: 'smooth' });
    },
    onScroll() {
      this.showButton = window.pageYOffset > 0;
    }
  },
  mounted() {
    window.addEventListener('scroll', this.onScroll);
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.onScroll);
  },
};
</script>