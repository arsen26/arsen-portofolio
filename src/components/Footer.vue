<template>
  <div class="container">
    <v-row class="column-container-style">
      <v-col
        class="column-style-footer"
        v-for="(column, i) in columns"
        :class="{ 'first-column': i === 0 }"
        :key="i"
      >
        <h2 :class="{ 'first-column-title': i === 0 }" v-if="i == 0">
          Arsen <span class="last-name-style">Cenollari</span>
        </h2>
        <h3 class="column-title-style">{{ column.title }}</h3>
        <ul>
          <li
            class="list-element-style"
            v-for="(insideElement, index) in column.insideElements"
            :key="index"
          >
            <v-icon class="icon-style-at-footer" v-if="i !== 0">{{
              insideElement.path
            }}</v-icon>
            {{ insideElement.insideElementTitle }}
          </li>
        </ul>
      </v-col>
      <v-col>
        <v-text-field
          class="text-field-style"
          label="Send Email"
          append-inner-icon="mdi-email"
          variant="outlined"
          dense
        ></v-text-field>
      </v-col>
    </v-row>
    <div style="padding-top: 30px">
      <v-divider></v-divider>
      <v-footer class="footer-style"
        >&reg; Arsen Cenollari - {{ currentYear }}</v-footer
      >
    </div>
  </div>
</template>

<script>
import SvgIcon from "@jamescoyle/vue-icon";
import { mdiEmailArrowRightOutline } from "@mdi/js";

export default {
  components: {
    SvgIcon,
  },
  data() {
    return {
      currentYear: null,
      columns: [
        {
          title: "",
          insideElements: [{ insideElementTitle: "Front End Developer" }],
        },
        {
          title: "Contact",
          insideElements: [
            { insideElementTitle: "Facebook", path: "mdi-facebook" },
            { insideElementTitle: "Instagram", path: "mdi-instagram" },
          ],
        },
        {
          title: "Navigate",
          insideElements: [
            { insideElementTitle: "Home", path: "mdi-home-circle" },
            { insideElementTitle: "Education", path: "mdi-school" },
            { insideElementTitle: "Projects", path: "mdi-projector-screen" },
          ],
        },
      ],
    };
  },
  methods: {
    getYear() {
      this.currentYear = new Date().getFullYear();
    },
  },
  created() {
    this.getYear();
  },
};
</script>

<style scoped>
.icon-style-at-footer {
  margin-bottom: 5px;
}
.footer-style {
  background-color: #04ecdc;
  opacity: 90%;
  height: 20px;
  box-shadow: 0 0 5px #04ecdc, 0 0 10px #04ecdc, 0 0 20px #04ecdc;
}
.column-style-footer {
  padding-right: 20px;
}
.text-field-style {
  height: 40px !important;
  color: white;
}
.container {
  background-color: #171a1e;
}
.last-name-style {
  color: #04ecdc;
  text-shadow: 0 0 5px #04ecdc, 0 0 10px #04ecdc, 0 0 20px #04ecdc,
    0 0 40px #04ecdc;
}
.first-column {
  padding-right: 70px;
}
.first-column-title {
  color: white;
  text-shadow: 0 0 5px #ffff, 0 0 10px #ffff, 0 0 20px #ffff, 0 0 40px #ffff;
}
.column-container-style {
  display: flex;
  padding: 20px;
}
.column-title-style {
  font-family: "Roboto Mono", monospace !important;
  color: white;
  margin-left: 3px;
  text-shadow: 0 0 5px #ffff, 0 0 10px #ffff, 0 0 20px #ffff, 0 0 40px #ffff;
}
.list-element-style {
  font-family: "Roboto Mono", monospace !important;

  cursor: pointer;
  color: white;
  padding-top: 5px;
  align-items: center !important;
  text-shadow: 0 0 5px #ffff, 0 0 10px #ffff;
  list-style: none;
}

@media (max-width: 950px) {
  .column-container-style {
    display: grid;
    text-align: center;
    justify-content: center;
    align-items: center !important;
    align-content: center;
  }
  .column-title-style {
    color: white;
    text-shadow: 0 0 5px #ffff, 0 0 10px #ffff, 0 0 20px #ffff;
    font-size: 25px;
  }
  .first-column {
    justify-content: center;
    display: grid;
    text-align: center;
    margin-left: 25px;
  }
}
</style>
