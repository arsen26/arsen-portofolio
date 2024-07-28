<template>
  <div>
    <isLoadingComponent :isLoading="isLoading" />
    <v-app class="entire-app">
      <v-main>
        <SideMenu class="menu-navigation-bar" />
        <Hero />
        <EducationVue />
        <Projects />
        <Services />
        <contactMe />
        <Footer />
      </v-main>
    </v-app>
  </div>
</template>

<script>
import SideMenu from "./components/SideMenu.vue";
import Hero from "./components/Hero.vue";
import EducationVue from "./components/Education.vue";
import Services from "./components/Services.vue";
import Footer from "./components/Footer.vue";
import Projects from "./components/Projects.vue";
import contactMe from "./components/contactMe.vue";
import isLoadingComponent from "./components/isLoading.vue";

export default {
  name: "App",
  components: {
    SideMenu,
    Hero,
    EducationVue,
    Services,
    Footer,
    Projects,
    contactMe,
    isLoadingComponent,
  },
  data() {
    return {
      isLoading: true,
    };
  },
  created() {
    setTimeout(() => {
      this.isLoading = false;
    }, 5000);
  },
};
</script>

<style scoped>
.menu-navigation-bar {
  position: fixed;
  top: 0;
  width: 100%;
  z-index: 1000;
}
.entire-app {
  position: relative;
  min-height: 100vh;
  overflow: hidden;
}
</style>
