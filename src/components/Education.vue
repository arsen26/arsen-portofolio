<template>
  <div class="education-container">
    <v-row style="color: black; text-align: center">
      <v-col>
        <h2 class="education-word-style">Education and trainings</h2>
      </v-col>
    </v-row>
    <v-row class="justify-center align-center">
      <v-col>
        <v-timeline align="center">
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
          title: "High School Diploma",
          description:
            "Completed high school with excellent results, showcasing perseverance and dedication to learning. This period helped me build a strong foundation for future academic and professional growth.",
        },
        {
          year: 2023,
          title: "Bachelor's in Computer Science",
          description:
            "Graduated from the University of Tirana, gaining skills in C, C++, HTML, CSS, JavaScript, teamwork, and project development. This experience strengthened my problem-solving abilities and technical expertise.",
        },
        {
          year: 2023,
          title: "Internship at 2RM Lab",
          description:
            "Worked with Vue.js and JavaScript, developed reusable components, solved programming challenges, and used GitLab for version control. This internship allowed me to improve my coding skills and learn to work efficiently in a team environment.",
        },
        {
          year: "2023 - Now",
          title: "Front-End Developer at 2RM Lab",
          description:
            "Developed financial software using Vue.js, Vuex, Vuetify, and Vue Router, implementing CRUD, UI enhancements, and responsive web pages. This role has helped me refine my technical skills and contribute effectively to large-scale projects.",
        },
      ],
    };
  },
};
</script>

<style scoped>
.year-style {
  color: white;
}

.education-container {
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
  padding-bottom: 40px;
  text-align: center;
}

.text-container-timeline {
  font-family: "Roboto Mono", monospace;
  font-weight: 300;
  color: white;
  text-align: center;
}

.text-container-timeline-title {
  font-family: "Roboto Mono", monospace;
  font-weight: 700;
  color: white;
  text-align: center;
}

.timeline-container {
  background-color: #090809;
  box-shadow: 0 0 5px #04ecdc, 0 0 10px #04ecdc, 0 0 10px #04ecdc,
    0 0 30px #04ecdc;
  border-radius: 10px;
  padding: 20px;
  word-wrap: break-word;
  overflow-wrap: break-word;
  max-width: 600px; /* Shto një max-width për të mos u shtrirë shumë */
  margin: auto; /* E qendron në mes */
  transition: all 0.3s ease;
}

.timeline-container:hover {
  box-shadow: 0 0 5px #04ecdc, 0 0 15px #04ecdc, 0 0 20px #04ecdc,
    0 0 55px #04ecdc;
  transform: scale(1.01);
}

.neon-dot {
  box-shadow: 0 0 5px #04ecdc, 0 0 10px #04ecdc, 0 0 20px #04ecdc,
    0 0 40px #04ecdc !important;
}

@media (max-width: 800px) {
  .education-word-style {
    font-size: 60px;
    margin-top: 100px;
    line-height: 1;
  }
}
</style>
