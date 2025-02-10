<template>
  <div class="education-container">
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
          description: "I completed high school in 2020 with excellent results. During this period, I was recognized for my perseverance, strong will, and dedication to learning, demonstrating a consistent commitment to both academic and personal growth.",
        },
        {
          year: 2023,
          title: "University diploma",
          description: "I completed my Bachelor's in Computer Science in 2023 at the University of Tirana, where I gained knowledge in programming languages like C, C++, HTML, CSS, and JavaScript. I also worked as a designer on a conference platform project and developed skills in teamwork, deadlines, and basic networking and operating systems.",
        },
        {
          year: 2023,
          title: "Internship",
          description:
            "During my internship at 2RM Lab as a Front-End Development Intern, I gained valuable experience working with JavaScript and Vue.js. I developed strong teamwork and problem-solving skills, while learning to effectively analyze and address programming issues. I worked with Vue.js to create reusable components and build dynamic, data-driven applications. I also utilized GitLab for version control, collaboration, and project management, ensuring smooth workflows and efficient task management. This experience allowed me to enhance my technical abilities while contributing to the success of the team.",
        },
        {
          year: "2023 - Now",
          title: "Front End Developer",
          description:
            "At 2RM Lab, I worked extensively on developing a financial and managerial software using Vue.js, Vuex, Vuetify, and Vue Router. I implemented full CRUD functionalities, ensuring efficient data management. I also focused on maintaining the visual aspects of the app, adding new features, and fixing bugs. Additionally, I contributed to building responsive static web pages and developing dynamic web applications to improve user interactivity and data handling.",
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
