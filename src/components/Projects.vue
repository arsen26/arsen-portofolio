<template>
  <div class="project-container">
    <v-row>
      <span class="projects-title">Projects</span>
    </v-row>
    <v-row class="row-card-container">
      <v-col v-for="(project, index) in projects" :key="index">
        <v-card :key="index" class="mx-auto project-card-style" width="330">
          <v-img
            class="align-end text-white"
            height="200"
            :src="project.image"
            cover
          >
            <v-card-title class="project-title">{{
              project.title
            }}</v-card-title>
          </v-img>
          <v-card-text>
            <div>{{ project.subtitle }}</div>
            <div>{{ project.description }}</div>
          </v-card-text>

          <v-card-actions>
            <v-btn
              @click="sendToGitHub(project.github)"
              color="#021526"
              text="Explore"
            ></v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </div>
</template>

<script>
import AnnaPhotographers from "@/assets/anna-photographers.png";
import AceShare from "@/assets/Ace2.png";
export default {
  data() {
    return {
      AnnaPhotographers,
      projects: [
        {
          title: "Anna Photographers",
          subtitle: "Photography project",
          description: "Website for Photography Studio",
          image: AnnaPhotographers,
          github: "https://github.com/arsen26/anna-photographers-vue3",
        },
        {
          title: "Ace Share",
          subtitle: "Personal project",
          description: "You can share folders from pc to your phone.",
          image: AceShare,
          github:
            "https://github.com/arsen26/qr-code-folder-share/tree/2-monitor-version",
        },
      ],
    };
  },
  methods: {
    sendToGitHub(itemGit) {
      window.open(`${itemGit}`, "_blank");
    },
  },
};
</script>

<style scoped>
.project-title {
  background-color: rgba(0, 0, 0, 0.5); /* Black with 50% transparency */
}
.project-card-style:hover {
  transform: scale(1.01);
  box-shadow: 0 0 5px #04ecdc, 0 0 15px #04ecdc, 0 0 20px #04ecdc,
    0 0 55px #04ecdc;
}
.project-card-style {
  height: 350px;
}
.row-card-container {
  display: flex;
  flex-direction: row;
  padding-left: 20px;
  padding-right: 20px;
}
.projects-title {
  font-family: "Russian Dollmaker";
  margin-top: 100px;
  font-size: 100px;
  font-weight: 100;
  color: white;
  padding-bottom: 40px;
}
.project-container {
  background-color: #222831;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
