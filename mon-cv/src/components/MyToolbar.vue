<template>
  <div>
    <v-app-bar dark color="var(--primary-color)" clipped-left app >
        <v-avatar id="logo" width="150px" height="45px" style="padding: 52px" >
          <img :src="require('@/assets/images/logoSm.png')" alt="logo">
        </v-avatar>
        <v-spacer></v-spacer>
        <v-tabs
            v-if="$vuetify.breakpoint.lgAndUp"
            v-model="tab"
            centered
            color="tabs"
        >
          <v-tab v-for="(menu,index) in menus" :key="index" :value="index" @click="scrollToComponent(menu.root)">{{menu.title}}</v-tab>
        </v-tabs>
        <v-spacer></v-spacer>
        <v-btn v-if="$vuetify.breakpoint.lgAndUp" color="transparent" @click="printPage"><v-icon v-if="!loading">
          mdi-printer
        </v-icon>
          <v-progress-circular v-if="loading" indeterminate size="30"></v-progress-circular>
        </v-btn>
        <v-spacer></v-spacer>
        <v-btn
            v-if="$vuetify.breakpoint.mdAndDown"
            id="menu-activator"
            color="transparent"
        >
          <v-icon>
            mdi-menu
          </v-icon>
        </v-btn>
        <v-menu
            activator="#menu-activator"
            transition="slide-y-transition"
        >
          <v-list>
            <v-list-item
                v-for="(item, index) in menus"
                :key="index"
                :value="index"
                @click="scrollToComponent(item.root)"
            >
              <v-list-item-title>{{ item.title }}</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>


    </v-app-bar>
  </div>
</template>

<script>
import "../assets/css/toolbar.css";
import html2canvas from 'html2canvas';
import jsPDF from 'jspdf';
export default {
  name: 'myToolbar',
  data: function () {
    return {
      tab: null,
      loading: false,
      menus:[
        {title:"About",root:"about-me"},
        {title:"Professional Experience",root:"experience"},
        {title:"Education",root:"education"},
        {title:"Stack Technlogy",root:"stack"},
        {title:"Hobbies",root:"hobbies"},
        {title:"Contact",root:"contact"}
      ]
    }
  },
  methods: {
    scrollToComponent(root) {
      const element = this.$parent.$parent.$refs[root]
      if (element) {
        element.$el.scrollIntoView({behavior: 'smooth'})
      }
    },
    printPage() {
        this.loading = true;
        const content = document.getElementById('app');
        html2canvas(content).then(canvas => {
          const pdf = new jsPDF();
          pdf.addImage(canvas.toDataURL('image/png'), 'PNG', 0, 0, pdf.internal.pageSize.getWidth(), pdf.internal.pageSize.getHeight());
          pdf.save('farah_ouaddane_cv.pdf');
          this.loading = false;
        });

    }
  }
}
</script>

