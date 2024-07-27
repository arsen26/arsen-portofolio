<template>
  <v-card class="menu">
    <v-layout>
      <v-toolbar class="toolbar">
        <h3 class="name-style">
          Arsen <span class="last-name-style">Cenollari</span>
        </h3>
        <v-spacer></v-spacer>
        <v-btn
          variant="text"
          class="button-style"
          v-for="(item, index) in menuItems"
          :key="index"
        >
          <span>{{ item.title }}</span>
        </v-btn>
      </v-toolbar>
      <v-main style="height: 250px"></v-main>
    </v-layout>
  </v-card>
</template>
<script>
export default {
  data() {
    return {
      menuItems: [
        { title: "Home" },
        { title: "Education" },
        { title: "Contact" },
        { title: "Projects" },
      ],
    };
  },
};
</script>
<style scoped>
.menu {
  background-color: #222831;
  border-radius: 0px;
  height: 70px;
}
.toolbar {
  background-color: #171a1e;
}
.button-style {
  color: white;
}
.button-style:hover {
  color: #04ecdc;
  text-shadow: 0 0 5px #04ecdc, 0 0 10px #04ecdc, 0 0 20px #04ecdc,
    0 0 40px #04ecdc;
}
.last-name-style {
  color: #04ecdc;
  text-shadow: 0 0 5px #04ecdc, 0 0 10px #04ecdc, 0 0 20px #04ecdc,
    0 0 40px #04ecdc;
}
.name-style {
  padding-left: 15px;
  color: white;
  text-decoration: none !important;
  text-shadow: 0 0 5px #ffff, 0 0 10px #ffff, 0 0 20px #ffff, 0 0 20px #ffff;
}
</style>
