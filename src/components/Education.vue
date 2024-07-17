<template>
  <v-container class="container">
    <v-row style="color: white; text-align: center">
      <v-col>
        <h2 class="education-word-style">Education and trainings</h2>
      </v-col>
    </v-row>
    <v-row style="max-width: 90vw">
      <v-col>
        <v-timeline align="start">
          <v-timeline-item
            dot-color="#04ECDC"
            fill-dot="true"
            class="timeline-point-style"
            v-for="(item, index) in content"
            key="index"
          >
            <template v-slot:opposite>
              <span class="text-container-timeline">
                {{ item.year }}
              </span>
            </template>
            <div>
              <div class="text-h6 text-container-timeline">
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
  </v-container>
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
          year: 2023 + "- Now",
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
.container {
  justify-content: center;
  align-content: center;
  display: flex;
  flex-direction: column;
}
.education-word-style {
  font-size: 40px;
}
.text-container-timeline {
  color: white !important;
}
</style>
