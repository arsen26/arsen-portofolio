<template>
  <div class="container">
    <div class="text-container" style="color: white">
      <h2 class="first-title-style">Hi, It's Arsen...</h2>
      <h1>I'm <span class="skills-style" id="typed"></span></h1>

      <p>
        ...a 22-year-old with a degree in Computer Science from the
        <a class="link-for-faculty" @click.prevent="openUniversity"
          >Faculty of Natural Sciences</a
        >
        in Tirana. After completing my studies, I started an internship and
        subsequently secured a position as a Front-End Developer, where I have
        now accumulated over a year of experience.
      </p>
      <i class="bx social-media-icon bxl-instagram"></i>

      <i class="bx social-media-icon bxl-facebook"></i>
      <i class="bx social-media-icon bxl-linkedin"></i>
      <i class="bx social-media-icon bxl-github"></i>
    </div>
    <div class="image-container">
      <img
        class="image-hero-style"
        :width="300"
        :src="ProfilePhoto"
        alt="Profile Photo"
      />
    </div>
  </div>
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
        strings: ["Front End Developer", "a UI/UX Designer"],
        typeSpeed: 40,
        backSpeed: 50,
        loop: true,
      });
    },
    openUniversity() {
      var url = "https://fshn.edu.al/";
      window.open(url, "_blank").focus();
    },
  },
};
</script>

<style scoped>
.link-for-faculty {
  text-decoration: none;
  color: white;
}
.link-for-faculty:hover {
  cursor: pointer;
  text-decoration: none;
  color: #04ecdc;
  text-shadow: 0 0 5px #04ecdc, 0 0 10px #04ecdc, 0 0 20px #04ecdc;
}
.first-title-style {
  font-size: 55px;
}
.social-media-icon {
  font-size: 35px;
}
.social-media-icon:hover {
  cursor: pointer;
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
  position: relative;
  padding-top: 100px;
  padding-bottom: 50px;
  width: 100% !important;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  background-color: #090809;
}

.text-container {
  max-width: 60% !important;
  padding-left: 15%;
  padding-right: 0px;
}
.image-container {
  flex-shrink: 0;
  margin-right: 10%;
}
.skills-style {
  color: #04ecdc;
  text-shadow: 0 0 5px #04ecdc, 0 0 10px #04ecdc, 0 0 20px #04ecdc;
}
</style>
