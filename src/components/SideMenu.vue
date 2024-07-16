<template>
  <v-card class="menu">
    <v-layout>
      <v-toolbar class="toolbar">
        <v-toolbar-title style="color: white">Arsen Cenollari</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-btn
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
  height: 60px;
}
.toolbar {
  background-color: #090809;
}
.button-style {
  color: white;
}
.button-style:hover{
    color: #04ECDC;
    text-shadow: 0 0 5px #04ECDC, 0 0 10px #04ECDC, 0 0 20px #04ECDC, 0 0 40px #04ECDC;

}

</style>
