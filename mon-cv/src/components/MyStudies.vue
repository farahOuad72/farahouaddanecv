<template>
  <v-card
      class="mx-auto my-12"
  >
    <div class="card-headers">
      <h2 class="about-me">Education</h2>
    </div>
    <v-timeline>
      <v-timeline-item
          class="timeline-edu"
          size="small"
          icon="mdi-school"
          v-for="(edu,index) in edus"
          :key="index"
      >
        <div class="mb-6" :style="cardStyle(index)">
          <div class="font-weight-normal">
            <strong>{{ edu.period }}</strong> | <span class="school">{{ edu.school }}</span>
          </div>
          <div>{{ edu.diploma }}</div>
        </div>
      </v-timeline-item>
    </v-timeline>

  </v-card>
</template>

<script>
export default {
  name: "MyStudies",
    data: () => ({
      edus: [
        { "period": "2017-2018",
          "school": "Ibn Abbad High school, Marrakech,Morocco",
          "diploma": "High School Diploma in Mathematical sciences"
        },
        { "period": "2018-2020",
          "school": "Ensa, Agadir,Morocco",
          "diploma": "Preparatory Classes"
        },
        { "period": "2020-2023",
          "school": "Ensisa, Mulhouse,France",
          "diploma": "Computer and Network Engineering Diploma"
        }
      ],
    }),
  methods: {
    cardStyle(index) {
      if (index % 2 === 1) {
        return "float: right;"
      } else {
        return ""
      }
    }
  }
}
</script>

<style scoped>
.school{
  color: var(--primary-color);
}

</style>