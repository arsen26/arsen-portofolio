<template>
  <v-app class="entire-app">
    <v-main>
      <SideMenu/>
      <Hero/>
      <EducationVue/>
      <Services/>
    </v-main>
  </v-app>
</template>

<script>
import SideMenu from './components/SideMenu.vue';
import Hero from './components/Hero.vue'
import EducationVue from './components/Education.vue';
import Services from './components/Services.vue'
export default {
  name: 'App',

 components:{
    SideMenu,
    Hero,
    EducationVue,
    Services
 },

  data: () => ({
    //
  }),
}
</script>
<style scoped>
  /* .entire-app{
    background-color: #090809;
  } */
</style>