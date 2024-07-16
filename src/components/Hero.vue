<template>
  <v-container class="container">
    <div>
        <h2>
            Hi, It's Arsen
        </h2>
        Hello i am arsen cenollari
    </div>
    <div>
      <v-img
        :width="300"
        aspect-ratio="16/9"
        cover
        src="https://cdn.vuetifyjs.com/images/parallax/material.jpg"
      ></v-img>
    </div>
  </v-container>
</template>

<script>
 
export default {
  data() {
    return {};
  },
};
</script>

<style scoped>
.container {
  display: flex;
}
</style>
