<template>
  <v-app class="entire-app">
    <v-main>
      <SideMenu/>
      <Hero/>
      <EducationVue/>
    </v-main>
  </v-app>
</template>

<script>
import SideMenu from './components/SideMenu.vue';
import Hero from './components/Hero.vue'
import EducationVue from './components/Education.vue';
export default {
  name: 'App',

 components:{
    SideMenu,
    Hero,
    EducationVue
 },

  data: () => ({
    //
  }),
}
</script>
<style scoped>
  .entire-app{
    background-color: #090809;
  }
</style>