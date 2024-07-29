<template>
  <v-card v-if="width > 800" class="menu">
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

  <v-app-bar v-if="width < 800" color="#171a1e" prominent>
    <v-row class="row-icon-mobile-holder">
      <v-app-bar-nav-icon
    style="color: white;"
      variant="text"
      @click.stop="drawer = !drawer"
    ></v-app-bar-nav-icon>  
    </v-row>
    
    <v-spacer></v-spacer>
  </v-app-bar>

  <v-navigation-drawer style="background-color: #222831 !important; color: white;" v-model="drawer" temporary   location="right">
  <v-list>
    <v-list-item
      v-for="(item, index) in menuItems"
      :key="index"
      :title="item.title"
      link
    ></v-list-item>
  </v-list>
</v-navigation-drawer>
</template>

<script>
import { ref, onMounted, onBeforeUnmount } from "vue";

export default {
  setup() {
    const drawer = ref(false);
    const width = ref(window.innerWidth);
    const menuItems = ref([
      { title: "Home" },
      { title: "Education" },
      { title: "Contact" },
      { title: "Projects" },
    ]);

    const measureWidth = () => {
      width.value = window.innerWidth;
    };

    const handleResize = () => {
      measureWidth();
    };

    onMounted(() => {
      measureWidth();
      window.addEventListener("resize", handleResize);
    });

    onBeforeUnmount(() => {
      window.removeEventListener("resize", handleResize);
    });

    return { width, menuItems, drawer };
  },
};
</script>

<style scoped>
.row-icon-mobile-holder{
  width: 100%;
  justify-content: end;
}
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
