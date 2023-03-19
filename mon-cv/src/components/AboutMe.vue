<template>
  <v-card
      class="mx-auto my-12"
  >
    <div class="card-headers">
      <h2 class="about-me">About me</h2>
    </div>
    <v-row>
      <v-col sm="4" class="photo-aboutme">
        <div class="d-flex justify-center align-center">
          <v-avatar
              id="avatar-photo"
              rounded="0"
          >
            <v-img id="myphoto" cover :src="require('@/assets/images/moi.png')" alt="moi"></v-img>
          </v-avatar>

        </div>
        <v-card-title class="d-flex justify-center align-center">Farah Ouaddane</v-card-title>

      </v-col>
      <v-col sm="8">
        <v-card-title v-if="$vuetify.breakpoint.lgAndUp">
        </v-card-title>
        <v-card-text class="desc-aboutme">
          <div>I am a soon-to-be software engineer and currently a web back-end developer apprentice with a forever growing love for coding.
            <br/>
            My studies have provided me with a strong foundation in programming languages, algorithms, and data structures.
            <br/>
            Throughout my apprenticeship, I have been actively involved in building and maintaining web applications, with a focus on back-end development.
            <br/>
            I am a detail-oriented individual with a strong work ethic and I am eager to continue learning and growing as a developer.
            <br/>
            I am excited about the endless possibilities that technology offers and look forward to contributing my skills to create innovative solutions.</div>
        </v-card-text>

        <v-divider class="mx-4 mb-1"></v-divider>

        <v-card-title>Soft Skills</v-card-title>

        <v-col class="chip-group">
          <v-chip color="var(--third-color)" v-for="(key,index) in keys" :key="index" :value="index">{{key}}</v-chip>
        </v-col>

        <v-divider class="mx-4 mb-1"></v-divider>
        <v-card-title>Languages</v-card-title>
        <v-list density="compact">
          <v-list-item
              v-for="(item, i) in languages"
              :key="i"
              :value="item"
              active-color="primary"
          >
            <v-list-item-title>{{item.text}} : {{item.level}}</v-list-item-title>
          </v-list-item>
        </v-list>

      </v-col>

    </v-row>

  </v-card>
</template>

<script>
export default {
  name: "AboutMe",

  data: () => ({
    keys:["Communication","Problem-solving","Adaptability","Teamwork","Creativity"],
    languages: [
      { text: 'Arabe', level: 'Bilingual' },
      { text: 'Français', level: 'Bilingual' },
      { text: 'Anglais', level: 'Fluent (B2)' }
    ]

  }),

  methods: {

  },

}
</script>

<style scoped>
#myphoto{
  border-radius: 50% 30% / 20% 10%;
  width: 9rem;
  height: 95%;
}
.desc-aboutme{
  text-align: justify;
}
.v-slide-group__content{
  padding: 10px !important;
  width: 100% !important;
  display: inline-flex !important;
  flex: none !important;
}
.v-chip.v-size--default {
  font-size: inherit;
}
.chip-group{
  width: max-content !important;
}
.chip-group .v-chip{
  margin: 5px !important;
}
.v-card__title{
  padding-bottom: 0 !important;
}
.v-list-item{
  min-height: 25px !important;
}
.v-list{
  padding-left: 1em;
}
</style>