<template>
  <div
    style="
      justify-content: center;
      align-items: center;
      background-color: #222831;
    "
  >
    <div class="container" v-if="!isMobileScreen">
      <v-row>
        <h1 class="title">Services</h1>
      </v-row>
      <v-row class="v-col-card-style" style="justify-content: center">
        <v-col v-for="(variant, i) in services" :key="i" cols="12" md="6">
          <v-card class="mx-auto v-card-style">
            <v-card-item class="card-text-container">
              <div>
                <span class="text-h6 mb-1 text-caption-title">
                  {{ variant.name }}
                </span>
                <div class="text-caption">{{ variant.description }}</div>
              </div>
            </v-card-item>
          </v-card>
        </v-col>
      </v-row>
    </div>

    <div class="container" v-else>
      <v-row>
        <h1 class="title">Services</h1>
      </v-row>
      <v-row class="expansion-style">
        <v-expansion-panels
          v-for="(variant, i) in services"
          class="my-2"
          variant="popout"
        >
          <v-expansion-panel
            class="expansion-panel-title"
            :key="i"
            style="border-radius: 8px !important"
            :text="variant.description"
            :title="variant.name"
          ></v-expansion-panel>
        </v-expansion-panels>
      </v-row>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      windowWidth: 0,
      isMobileScreen: false,
      services: [
        {
          name: "UI Design",
          description:
            "I offer professional UI design services, creating responsive web designs using Figma. My designs ensure a seamless user experience across various devices, making your website both visually appealing and user-friendly.",
        },
        {
          name: "Logo, Photo, and Video Editing",
          description:
            "I provide expert services in logo creation, as well as photo and video editing. Whether you need a new logo or want to enhance your visual content, I can help bring your creative vision to life.",
        },
        {
          name: "Front End Developer",
          description:
            "As a Front-End Developer with over a year of experience, I specialize in creating dynamic and responsive web applications. Utilizing Vue.js and Vuetify, I craft interactive and visually appealing user interfaces tailored to your needs. Whether you require a new website or enhancements to an existing project, I offer professional and reliable front-end development services to bring your vision to life.",
        },
        {
          name: "Web Performance and SEO",
          description:
            "I provide comprehensive web performance monitoring and SEO services to ensure your website runs efficiently and ranks well on search engines. My expertise includes optimizing website speed, improving user experience, and implementing effective SEO strategies to boost your online visibility and drive more traffic to your site.",
        },
      ],
    };
  },
  methods: {
    updateWindowWidth() {
      this.windowWidth = window.innerWidth;
      this.checkWidth();
    },
    checkWidth() {
      this.isMobileScreen = this.windowWidth < 950;
    },
  },
  mounted() {
    this.updateWindowWidth();
    window.addEventListener("resize", this.updateWindowWidth);
  },
  beforeDestroy() {
    window.removeEventListener("resize", this.updateWindowWidth);
  },
};
</script>
<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Roboto+Mono:ital,wght@0,100..700;1,100..700&display=swap");
.text-caption {
  font-family: "Roboto Mono", monospace !important;
  font-weight: 400;
}
.text-caption-title {
  font-family: "Roboto Mono", monospace !important;
}
.title {
  font-family: "Russian Dollmaker";
  margin-top: 100px;
  font-size: 100px;
  font-weight: 100;
  color: white;
  padding-bottom: 10px;
}
.card-text-container {
  padding: 20px;
}
.v-col-card-style {
  max-width: 80%;
  padding-left: 50px;
  padding-right: 50px;
}
.v-card-style {
  background-color: #04ecdc;
  height: 200px;
  border-radius: 15px;
  transition: all 0.3s ease;
  /* opacity: 85%; */
}

.v-card-style:hover {
  background-color: #04ecdc;
  box-shadow: 0 0 5px #04ecdc, 0 0 10px #04ecdc, 0 0 20px #04ecdc,
    0 0 20px #04ecdc;
  height: 200px;
  border-radius: 15px;
  transform: scale(1.01);
}

@media (max-width: 950px) {
  .v-card-style {
    background-color: #04ecdc;
    height: max-content;
    border-radius: 15px;
  }
  .v-card-style:hover {
    background-color: #04ecdc;
    box-shadow: 0 0 5px #04ecdc, 0 0 10px #04ecdc, 0 0 20px #04ecdc,
      0 0 20px #04ecdc;
    height: max-content;
    border-radius: 15px;
    transform: scale(1.01);
  }
}

@media (min-width: 1150px) and (max-width: 1500px) {
  .v-card-style {
    background-color: #04ecdc;
    height: 230px;
    border-radius: 15px;
  }
  .v-card-style:hover {
    background-color: #04ecdc;
    box-shadow: 0 0 5px #04ecdc, 0 0 10px #04ecdc, 0 0 20px #04ecdc,
      0 0 20px #04ecdc;
    height: 230px;
    border-radius: 15px;
    transform: scale(1.01);
  }
  .card-text-container {
    padding-bottom: 20px;
  }
}
@media (min-width: 950px) and (max-width: 1155px) {
  .v-card-style {
    background-color: #04ecdc;
    height: 290px;
    border-radius: 15px;
  }
  .v-card-style:hover {
    background-color: #04ecdc;
    box-shadow: 0 0 5px #04ecdc, 0 0 10px #04ecdc, 0 0 20px #04ecdc,
      0 0 20px #04ecdc;
    height: 290px;
    border-radius: 15px;
    transform: scale(1.01);
  }
  .card-text-container {
    padding-bottom: 20px;
  }
}

@media (max-width: 959px) {
  .v-card-style {
    background-color: #04ecdc;
    height: max-content;
    border-radius: 15px;
  }
  .v-card-style:hover {
    background-color: #04ecdc;
    box-shadow: 0 0 5px #04ecdc, 0 0 10px #04ecdc, 0 0 20px #04ecdc,
      0 0 20px #04ecdc;
    height: max-content;
    border-radius: 15px;
    transform: scale(1.01);
  }
}

.container {
  padding-top: 50px;
  padding-bottom: 80px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.expansion-style {
  padding-left: 40px;
  padding-top: 10px;
  padding-right: 40px;
}
.description-style {
  padding-left: 20px;
  padding-right: 20px;
}
.expansion-panel-title {
  font-family: "Roboto Mono", monospace !important;
  background-color: #04ecdc;
  /* padding-top: 20px; */
  align-items: center;
}
</style>
