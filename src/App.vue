<template>
  <div>
    <isLoadingComponent :isLoading="isLoading" />
    <v-app class="entire-app">
      <v-main>
        <SideMenu @scroll-to="scrollToSection" class="menu-navigation-bar" />
        <Hero id="home-container" />
        <EducationVue id="education-container" />
        <Projects id="projects-container" />
        <Services id="services-container" />
        <contactMe id="contact-container" />
        <Footer />
      </v-main>
    </v-app>
  </div>
</template>

<script>
import { ref, nextTick, onMounted } from "vue";
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
  setup() {
    const isLoading = ref(true);

    const scrollToSection = async (sectionId) => {
      await nextTick();
      console.log(sectionId);
      const section = document.getElementById(sectionId);
      console.log(section, "=-=>> section");
      if (section) {
        section.scrollIntoView({ behavior: "smooth" });
      }
    };

    onMounted(() => {
      setTimeout(() => {
        isLoading.value = false;
      }, 5000);
    });

    return { isLoading, scrollToSection };
  },
};
</script>

<style scoped>
.menu-navigation-bar {
  position: fixed ;
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
