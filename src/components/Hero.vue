<template>
  <div class="container">
    <div class="text-container" style="color: white">
      <h2 class="first-title-style">Hi, It's Arsen...</h2>
      <h1>I'm <span class="skills-style" id="typed"></span></h1>

      <p class="paragraph-about-me-style">
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
      <i class="bx social-media-icon bx-news"></i>
      <v-row style="padding-top: 10px">
        <v-btn
          class="ma-2 download-cv-button"
          outlined
          :href="pdfUrl"
          download="arsen-cenollari.pdf"
          prepend-icon="mdi-newspaper-variant-multiple"
          ><span style="font-family: 'Roboto Mono', monospace !important">
            Download CV
          </span></v-btn
        >
      </v-row>
    </div>

    <v-spacer></v-spacer>
    <div class="image-container">
      <img class="image-hero-style" :src="ProfilePhoto" alt="Profile Photo" />
      <img
        class="background-image"
        :src="BackgroundImage"
        alt="Profile Photo"
      />
    </div>
  </div>
</template>

<script>
import Typed from "typed.js";
import "boxicons/css/boxicons.min.css";
import ProfilePhoto from "@/assets/arsen-linkedin.png";
import BackgroundImage from "@/assets/background-linkedin.png";
import pdfUrl from "@/assets/arsen-cenollari.pdf";

export default {
  data() {
    return {
      ProfilePhoto,
      BackgroundImage,
      pdfUrl,
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
  padding-top: 45px;
  font-family: "Russian Dollmaker";
  font-weight: 100;
  font-size: 105px;
}
.social-media-icon {
  font-size: 35px;
  transition: all 0.3s ease;
}

.social-media-icon:hover {
  cursor: pointer;
  font-size: 37px;
  color: #04ecdc;
  text-shadow: 0 0 5px #04ecdc, 0 0 10px #04ecdc, 0 0 20px #04ecdc;
}

@keyframes glow {
  0%,
  100% {
    color: white;
    text-shadow: none;
  }
  50% {
    color: #04ecdc;
    text-shadow: 0 0 5px #04ecdc, 0 0 10px #04ecdc, 0 0 20px #04ecdc;
  }
}

.bxl-instagram {
  animation: glow 2s infinite;
  animation-delay: 0s;
}

.bxl-facebook {
  animation: glow 2s infinite;
  animation-delay: 0.5s;
}

.bxl-linkedin {
  animation: glow 2s infinite;
  animation-delay: 1s;
}

.bxl-github {
  animation: glow 2s infinite;
  animation-delay: 1.5s;
}

.bx-news {
  animation: glow 2s infinite;
  animation-delay: 2s;
}
.image-hero-style {
  position: absolute;
  top: 50%;
  /* left: 50%; */
  transform: translate(-20%, -30%);
  width: 16vw;
  filter: drop-shadow(0rem 0rem 1.95rem #04ecdc);
  z-index: 1;
}

.background-image {
  width: 42vw;
  transform: translate(-36%, 30%);
}

@media (min-width: 800px) {
  .container {
    position: relative;
    padding-top: 100px;
    padding-bottom: 50px;
    width: 100% !important;
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    align-items: center;
    background-color: #222831;
  }
}
@media (max-width: 800px) {
  .container {
    padding-bottom: 50px;
    width: 100% !important;
    display: flex;
    flex-direction: column;
    align-items: center !important;
    justify-content: center !important;
    background-color: #222831;
    position: relative;
  }
  .first-title-style {
    padding-top: 45px;
    font-family: "Russian Dollmaker";
    font-weight: 100;
    font-size: 105px;
    line-height: 0.8;
  }

  .text-container {
    position: relative;
    margin-bottom: 120px;
    z-index: 1;
  }

  .image-container {
    width: 100%;
    display: grid;
    align-items: center;
    justify-content: center;
  }

  .image-container img {
    width: 80%;
    height: auto;
    margin-left: 130px;
  }

  .paragraph-about-me-style {
    position: relative;
    margin-top: 80px;
  }

  .skills-style {
    position: absolute;
    margin-top: 30 !important; /* Po përdorim top për të mbajtur fjali në një vend */
  }
}

.text-container {
  max-width: 60% !important;
  padding-left: 5%;
  /* padding-right: 10px !important; */
}
.image-container {
  align-items: center !important;
  position: relative;
  width: 350px;
  height: fit-content;
  margin-right: 70px;
  margin-bottom: 120px;
}
.skills-style {
  font-family: "Roboto Mono", monospace !important;
  color: #04ecdc;
  text-shadow: 0 0 5px #04ecdc, 0 0 10px #04ecdc, 0 0 20px #04ecdc;
}
.paragraph-about-me-style {
  font-family: "Roboto Mono", monospace !important;
  /* max-width: 400px; */
}
.download-cv-button {
  color: #04ecdc;
  background-color: #171a1e;
}
.download-cv-button:hover {
  color: #04ecdc;
  background-color: #171a1e;
  text-shadow: 0 0 5px #04ecdc, 0 0 10px #04ecdc, 0 0 20px #04ecdc;
  box-shadow: 0 0 5px #04ecdc, 0 0 15px #04ecdc, 0 0 20px #04ecdc;
}
</style>
