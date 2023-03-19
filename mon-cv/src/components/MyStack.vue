<template>
  <v-card
      class="mx-auto my-12"
  >
    <div class="card-headers">
      <h2 class="about-me">Stack Technology</h2>
    </div>
    <div class="stack-content row">
      <div class="col-12 col-md-3 stack-item">
        <v-card-title>Backend</v-card-title>
        <div class="image-grid">
          <v-img
              v-for="logoBack in logosBack"
              :key="logoBack.title"
              :src="logoBack.link"
              :alt="logoBack.title"
              :width="50"
          ></v-img>
        </div>
      </div>
      <div class="col-12 col-md-3 stack-item">
        <v-card-title>Frontend</v-card-title>
        <div class="image-grid">
          <v-img
              v-for="logoFront in logosFront"
              :key="logoFront.title"
              :src="logoFront.link"
              :alt="logoFront.title"
              :width="50"
          ></v-img>
        </div>
      </div>
      <div class="col-12 col-md-3 stack-item">
        <v-card-title>Devops</v-card-title>
        <div class="image-grid">
          <v-img
              v-for="logoDevops in logosDevops"
              :key="logoDevops.title"
              :src="logoDevops.link"
              :alt="logoDevops.title"
              :width="50"
          ></v-img>
        </div>
      </div>
      <div class="col-12 col-md-3 stack-item">
        <v-card-title>Data</v-card-title>
        <div class="image-grid">
          <v-img
              v-for="logoData in logosData"
              :key="logoData.title"
              :src="logoData.link"
              :alt="logoData.title"
              :width="70"
          ></v-img>
        </div>
      </div>
      <div v-bind:class="{ 'content-middle': $vuetify.breakpoint.lgAndUp }" style="width: 100%;">
        <div class="col-12 col-md-3 stack-item">
          <v-card-title>Mobile</v-card-title>
          <div class="image-grid">
            <v-img
                v-for="logoMobile in logosMobile"
                :key="logoMobile.title"
                :src="logoMobile.link"
                :alt="logoMobile.title"
                :width="100"
            ></v-img>
          </div>
        </div>
        <div class="col-12 col-md-3 stack-item">
          <v-card-title>Project Management</v-card-title>
          <div class="image-grid">
            <v-img
                v-for="logoManagement in logosManagement"
                :key="logoManagement.title"
                :src="logoManagement.link"
                :alt="logoManagement.title"
                :width="50"
            ></v-img>
          </div>
        </div>
        <div class="col-12 col-md-3 stack-item">
          <v-card-title>IDE</v-card-title>
          <div class="image-grid">
            <v-img
                v-for="logoIDE in logosIDE"
                :key="logoIDE.title"
                :src="logoIDE.link"
                :alt="logoIDE.title"
                :width="50"
            ></v-img>
          </div>
        </div>
      </div>


    </div>


  </v-card>
</template>

<script>
export default {
  name: "MyStack",
  data: () => ({
    logosBack: [
      {
        title: "MangoDb",
        link: require("@/assets/images/logo_mango.png")
      },
      {
        title: "PostgreSql",
        link: require("@/assets/images/logo_postgresql.png")
      },
      {
        title: "MariaDb",
        link: require("@/assets/images/logo_maria.png")
      },
      {
        title: "MySql",
        link: require("@/assets/images/logo_mysql.png")
      },
      {
        title: "Ibexa",
        link: require("@/assets/images/logo_ibexa.png")
      },
      {
        title: "Php",
        link: require("@/assets/images/logo_php.png")
      },
      {
        title: "Java",
        link: require("@/assets/images/logo_java.png")
      },
      {
        title: "Symfony",
        link: require("@/assets/images/logo_symfony.png")
      },
      {
        title: "Drupal",
        link: require("@/assets/images/logo_drupal.png")
      },
    ],
    logosFront: [
      {
        title: "JS",
        link: require("@/assets/images/logo_js.png")
      },
      {
        title: "HTML",
        link: require("@/assets/images/logo_html.png")
      },
      {
        title: "CSS",
        link: require("@/assets/images/css.png")
      },
      {
        title: "VueJS",
        link: require("@/assets/images/logo_vue.png")
      }
    ],
    logosDevops: [
      {
        title: "Docker",
        link: require("@/assets/images/logo_docker.png")
      },
      {
        title: "Gitlab",
        link: require("@/assets/images/logo_gitlab.png")
      }
    ],
    logosData: [
      {
        title: "Apache Spark",
        link: require("@/assets/images/logo_spark.png")
      }
    ],
    logosManagement: [
      {
        title: "Redmine",
        link: require("@/assets/images/logo_redmine.png")
      },
      {
        title: "Jira",
        link: require("@/assets/images/logo_jira.png")
      }
    ],
    logosIDE: [
      {
        title: "Jetbrains",
        link: require("@/assets/images/logo_jetbrains.png")
      },
      {
        title: "XCode",
        link: require("@/assets/images/logo_xcode.png")
      },
      {
        title: "Anddroid Studio",
        link: require("@/assets/images/logo_android.png")
      }
    ],
    logosMobile:[
      {
        title: "Swift",
        link: require("@/assets/images/logo_swift.png")
      },
      {
        title: "Kotlin",
        link: require("@/assets/images/logo_kotlin.png")
      }
    ]
  })
}
</script>

<style scoped>
  .row{
    margin: 0 !important;
  }
  .stack-item{
    border-bottom: 1px solid var(--primary-color);
    text-align: center;
  }
  .stack-item .v-card__title{
    display: block;
  }
  .content-middle{
    display: flex;
    justify-content: center;
  }
  .image-grid div{
    display: inline-block;
    margin: 10px;
  }

</style>