<template>
  <v-app class="entire-app">
    <v-main>
      <SideMenu class="menu-navigation-bar"/>
      <Hero/>
      <EducationVue/>
      <Services/>
      <Footer/>
    </v-main>
  </v-app>
</template>

<script>
import SideMenu from './components/SideMenu.vue';
import Hero from './components/Hero.vue'
import EducationVue from './components/Education.vue';
import Services from './components/Services.vue'
import Footer from './components/Footer.vue'
export default {
  name: 'App',

 components:{
    SideMenu,
    Hero,
    EducationVue,
    Services,
    Footer
    
 },

  data: () => ({
    //
  }),
}
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