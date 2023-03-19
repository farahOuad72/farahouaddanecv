<template>
  <v-card
      class="mx-auto my-12"
  >
    <div class="card-headers">
      <h2 class="about-me">Hobbies</h2>
    </div>
    <v-container fluid class="hobbies">
      <v-row>
        <v-col
            md="6"
            v-for="card in cards"
            :key="card.title"
            cols="12"
        >
          <v-card @click="openDialog(card)">
            <v-img
                :src=card.src
                class="align-end"
                gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                height="200px"
                cover
            >
            </v-img>
            <v-card-title class="text-white" v-text="card.title"></v-card-title>
            <v-card-text>{{ card.desc }}</v-card-text>
          </v-card>
          <v-dialog v-if="dialog" v-model="dialog" max-width="500px">
            <v-card>
              <v-img :src="selectedCard.src" contain></v-img>
              <v-card-title>{{ selectedCard.title }}</v-card-title>
              <v-card-text>
                {{ selectedCard.long_desc }}
              </v-card-text>
            </v-card>
          </v-dialog>
        </v-col>
      </v-row>
    </v-container>
  </v-card>
</template>

<script>
export default {
  name: "MyHobbies",
  data: () => ({
    cards: [
      { title: 'Theater', src: require('@/assets/images/img_theater.jpg'),
        desc:"Five years of study in Theatre Arts, Marrakech Institution (2013-2018)",
        long_desc:"Studied theatre arts for five years, including courses in acting, directing, playwriting, and theatre history.\n" +
            "Participated in numerous theatre productions as an actor and crew member, gaining experience in all aspects of theatre production, from auditions to performance.\n" +
            "Developed skills in public speaking, improvisation and performance opportunities.",
        flex: 6
      },
      { title: 'Piano', src: require('@/assets/images/img_piano.jpg'),
        desc:"Six years of music theory and nine years of piano, Marrakech Conservatory (2008-2017)",
        long_desc: "Studied music theory for six years, covering topics such as notation, harmony, rhythm, and musical analysis.\n" +
            "Received piano instruction for nine years, developing skills in technique, interpretation, sight-reading, and performance.",
        flex: 6
      },
      { title: 'Painting', src: require('@/assets/images/img_painting.png'),
        desc:"Self-taught Painter",
        long_desc: "Developed painting skills since childhood, with a focus on portraits and other figurative works." +
            "Continuously learning and improving techniques through experimentation and study of other artists.",
        flex: 6
      },
      { title: 'Contemporary dance', src: require('@/assets/images/img_dance.jpg'),
        desc: "Contemporary dance training with Taoufiq Izeddiou at Al Mokhtabar III (2015)",
        long_desc: "Completed intensive training in contemporary dance under the instruction of acclaimed dancer and choreographer Taoufiq Izeddiou at Al Mokhtabar III.\n" +
            "Gained proficiency in contemporary dance techniques and styles, including improvisation, partnering, and floorwork.\n" +
            "Developed skills in musicality, spatial awareness, and expressiveness through performance opportunities and choreographic workshops.\n" +
            "Demonstrated discipline and dedication through daily practice and conditioning.\n" +
            "Collaborated with fellow dancers and choreographers to create original works, which were performed in various venues and festivals.",
        flex: 6
      }
    ],
    dialog: false,
    selectedCard: {},
  }),
  methods: {
    openDialog(selectedItem){
      this.selectedCard = selectedItem;
      this.dialog = true;
    }
  }
}
</script>

<style scoped>

</style>