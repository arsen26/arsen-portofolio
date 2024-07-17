<template>
  <v-container class="container">
    <div style="color: white">
      <h2 class="first-title-style">Hi, It's Arsen</h2>
      <h1>I'm <span class="skills-style" id="typed"></span></h1>
      <i class="bx social-media-icon bxl-instagram"></i>

      <i class="bx social-media-icon bxl-facebook"></i>
      <i class="bx social-media-icon bxl-linkedin"></i>

    </div>
    <div>
      <v-img
        class="image-hero-style"
        :width="300"
        aspect-ratio="16/9"
        cover
        :src="ProfilePhoto"
      ></v-img>
    </div>
  </v-container>
</template>

<script>
import Typed from "typed.js";
import "boxicons/css/boxicons.min.css";
import ProfilePhoto from "@/assets/arsen-linkedin.png";

export default {
  data() {
    return {
      ProfilePhoto,
    };
  },
  mounted() {
    this.transition();
  },
  methods: {
    transition() {
      new Typed("#typed", {
        strings: ["Front End Developer", "Web Designer"],
        typeSpeed: 40,
        backSpeed: 50,
        loop: true,
      });
    },
  },
};
</script>

<style scoped>
.first-title-style{
  font-size: 55px;
}
.social-media-icon {
  font-size: 35px;
}
.social-media-icon:hover{
  font-size: 37px;
  color: #04ecdc;
  text-shadow: 0 0 5px #04ecdc, 0 0 10px #04ecdc, 0 0 20px #04ecdc;

}
.image-hero-style {
  position: relative;
  width: 32vw;
  border-radius: 50%;
  filter: drop-shadow(0 0 0.75rem #04ecdc);
}
.container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}
.skills-style {
  color: #04ecdc;
  text-shadow: 0 0 5px #04ecdc, 0 0 10px #04ecdc, 0 0 20px #04ecdc;
}
</style>
