<template>
  <div class="container">
    <v-row style="color: black; text-align: center">
      <v-col>
        <h2 class="education-word-style">Education and trainings</h2>
      </v-col>
    </v-row>
    <v-row style="max-width: 90vw">
      <v-col>
        <v-timeline align="start">
          <v-timeline-item
            dot-color="#ffff"
            fill-dot="true"
            class="neon-dot"
            v-for="(item, index) in content"
            :key="index"
          >
            <template v-slot:opposite>
              <span class="year-style">
                {{ item.year }}
              </span>
            </template>
            <div class="timeline-container">
              <div class="text-container-timeline-title">
                {{ item.title }}
              </div>
              <p class="text-container-timeline">
                {{ item.description }}
              </p>
            </div>
          </v-timeline-item>
        </v-timeline>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  data() {
    return {
      content: [
        {
          year: 2020,
          title: "Highschool diploma",
          description: "gg ere",
        },
        {
          year: 2023,
          title: "University diploma",
          description: "gg ere",
        },
        {
          year: 2023,
          title: "Internship",
          description:
            "I started a new position job as a front end developer at 2RM Lab",
        },
        {
          year: "2023 - Now",
          title: "Front End Developer",
          description:
            "I started a new position job as a front end developer at 2RM Lab",
        },
      ],
    };
  },
};
</script>

<style scoped>
@import url("https://fonts.cdnfonts.com/css/russian-dollmaker");
@import url("https://fonts.googleapis.com/css2?family=Roboto+Mono:ital,wght@0,100..700;1,100..700&display=swap");

.year-style {
  color: white;
}
.container {
  background-color: #222831;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  min-height: 100vh;
  padding: 20px;
}

.education-word-style {
  font-family: "Russian Dollmaker";
  font-weight: 100;
  color: white;
  font-size: 100px;
  margin-top: 140px;
}

.text-container-timeline {
  font-family: "Roboto Mono", monospace;
  font-weight: 300;

  color: white;
}
.text-container-timeline-title {
  font-family: "Roboto Mono", monospace;
  font-weight: 700;
  color: white;
}

.timeline-container {
  background-color: #090809;
  box-shadow: 0 0 5px #04ecdc, 0 0 10px #04ecdc, 0 0 10px #04ecdc,
    0 0 30px #04ecdc;
  /* border: 2px solid #04ECDC; */
  border-radius: 10px;
  padding: 20px;
  word-wrap: break-word;
  overflow-wrap: break-word;
  width: 100%;
  transition: all 0.3s ease;
}

.timeline-container:hover {
  background-color: #090809;
  box-shadow: 0 0 5px #04ecdc, 0 0 15px #04ecdc, 0 0 20px #04ecdc,
    0 0 55px #04ecdc;
  /* border: 2px solid #04ECDC; */
  border-radius: 10px;
  padding: 20px;
  word-wrap: break-word;
  overflow-wrap: break-word;
  width: 100%;
  transform: scale(1.01);
}
.timeline-container:hover .text-container-timeline {
  color: white;
  text-shadow: 0 0 5px #04ecdc, 0 0 10px #04ecdc, 0 0 20px #04ecdc,
    0 0 40px #04ecdc;
}

.timeline-container:hover .text-container-timeline-title {
  color: white;
  text-shadow: 0 0 5px #ffffff, 0 0 10px #04ecdc, 0 0 20px #04ecdc,
    0 0 40px #ffffff;
}

.neon-dot {
  box-shadow: 0 0 5px #04ecdc, 0 0 10px #04ecdc, 0 0 20px #04ecdc,
    0 0 40px #04ecdc !important;
}
@media (max-width: 800px) {
  .education-word-style {
    font-family: "Russian Dollmaker";
    font-weight: 100;
    color: white;
    font-size: 100px;
    margin-top: 140px;
    line-height: 0.8 !important;
  }
}
</style>
