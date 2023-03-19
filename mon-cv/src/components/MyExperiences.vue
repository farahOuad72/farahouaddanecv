<template>
  <v-card
      class="mx-auto my-12"
  >
    <div class="card-headers">
      <h2 class="about-me">Professional Experience</h2>
    </div>
    <v-row>
      <div class="col-12 col-md-6 experience-item"
           v-for="(experience, i) in experiences"
           :key="i"
           >
        <v-card-title v-text="experience.title"></v-card-title>
        <v-card-subtitle>{{experience.firm}} | {{experience.period}}</v-card-subtitle>
        <v-list density="compact">
          <v-list-item-title><v-icon icon="mdi-tools" color="var(--primary-color)">mdi-tools</v-icon> Tools:</v-list-item-title>
          <v-list-item>{{ experience.tools.join(' - ') }}</v-list-item>
          <v-list-item-title> <v-icon icon="mdi-format-list-bulleted" color="var(--primary-color)">mdi-format-list-bulleted</v-icon> Tasks:</v-list-item-title>
          <v-list-item v-for="(task, i) in experience.tasks" :key="i" :value="task"><v-icon icon="mdi-chevron-right" color="var(--primary-color)" size="large">mdi-chevron-right</v-icon> {{ task }}</v-list-item>
        </v-list>
      </div>
    </v-row>

  </v-card>
</template>

<script>
export default {
  name: "MyExperiences",
  data() {
    return {
      experiences: [
        {
          firm: "Actimage,Colmar",
          period: '2022-2023 (Ongoing)',
          title: "Aprenticeship as a web developer",
          desc: "Worked on maintaining and building web sites.",
          tools: ["HTML / SCSS", "Ibexa", "Drupal", "MariaDB", "Solr", "Varnish", "Traefik", "MailHog", "Elastic Search", "Docker"],
          tasks: [
            "Identify and troubleshoot bugs.",
            "Enhance user experience.",
            "Add new features to the web site.",
            "improve website performance and scalability.",
            "Containerize and deploy the website.",
            "Ensure a visually appealing layout.",
            "Creating custom content types and designing website templates."
          ]
        },
        {
          firm: "DOING,Saint-étienne",
          period: '2021-2022',
          title: "Aprenticeship as a web developer",
          desc: "Worked on maintaining and building web sites.",
          tools: ["HTML / CSS", "MySQL", "Oracle", "E2DO (in-house framework based on PHP and JS)", "VueJS"],
          tasks: [
            "Led the end-to-end development of the platform.",
            "Add new features to the web site (Gantt, Messaging system, Electronic document signature...).",
            "Oversaw both front-end and back-end development.",
            "Met the needs of our clients in the construction industry.",
            "Ensure that the platform was scalable and user-friendly.",
            "Identify and troubleshoot bugs."
          ]
        }
      ]
    }
  }
}
</script>

<style scoped>
@media (max-width: 959px) {
  .experience-item{
    border-bottom: 1px solid var(--primary-color);
  }
  .v-list-item {
    min-height: 22px !important;
  }
}
@media (min-width: 960px) {
  .experience-item:not(:last-child) {
    border-right: 1px solid var(--primary-color);
  }
  .v-list-item{
    min-height: 30px !important;
  }

}

.row {
  margin: 0 !important;
}
.v-card__subtitle{
  text-align: right!important;
  color: var(--primary-color);
}
.v-list-item{
  padding-left: 30px !important;
}

</style>