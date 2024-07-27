<template>
  <div class="container">
    <v-row>
      <span class="projects-title">Projects</span>
    </v-row>
    <v-row class="row-card-container">
      <v-col v-for="(project, index) in projects">
        <v-card :key="index" class="mx-auto project-card-style" max-width="400">
          <v-img
            class="align-end text-white"
            height="200"
            :src="project.image"
            cover
          >
            <v-card-title>{{ project.title }}</v-card-title>
          </v-img>
          <v-card-text>
            <div>{{ project.subtitle }}</div>
            <div>{{ project.description }}</div>
          </v-card-text>

          <v-card-actions>
            <v-btn color="#021526" text="Explore"></v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </div>
</template>

<script>
import AnnaPhotographers from "@/assets/anna-photographers.png";
export default {
  data() {
    return {
      AnnaPhotographers,
      projects: [
        {
          title: "Anna Photographers",
          subtitle: "Photography project",
          description: "test",
          image: AnnaPhotographers,
        },
        {
          title: "Anna Photographers",
          subtitle: "Photography project",
          description: "test",
          image: AnnaPhotographers,
        },
      ],
    };
  },
};
</script>

<style scoped>
.project-card-style:hover {
  transform: scale(1.01);
  box-shadow: 0 0 5px #04ecdc, 0 0 15px #04ecdc, 0 0 20px #04ecdc,
    0 0 55px #04ecdc;
}
.row-card-container {
  display: flex;
  flex-direction: row;
}
.projects-title {
  font-family: "Russian Dollmaker";
  margin-top: 100px;
  font-size: 100px;
  font-weight: 100;
  color: white;
  padding-bottom: 80px;
}
.container {
  background-color: #222831;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
