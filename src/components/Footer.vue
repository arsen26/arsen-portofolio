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
          <h3
            v-if="i == 0"
            @click="openMap()"
            style="cursor: pointer"
            class="font-weight-light mt-3 text-style font-color"
          >
            Tirane, Albania
          </h3>

          <h3
            v-if="i == 0"
            @click="writeEmail()"
            style="cursor: pointer"
            class="font-weight-light text-style font-color"
          >
            Email: cenollariarsen7@gmail.com
          </h3>
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
    openMap() {
      window.open(
        "https://www.google.com/maps/place/Tirana,+Albania/@41.3242769,19.8064902,15z/data=!4m15!1m8!3m7!1s0x1350310470fac5db:0x40092af10653720!2sTirana,+Albania!3b1!8m2!3d41.3275459!4d19.8186982!16zL20vMDdtX2Y!3m5!1s0x1350310470fac5db:0x40092af10653720!8m2!3d41.3275459!4d19.8186982!16zL20vMDdtX2Y?entry=ttu",
        "_blank"
      );
    },

    writeEmail() {
      window.open("mailto:cenollariarsen7@gmail.com");
    },
  },
  created() {
    this.getYear();
  },
};
</script>

<style scoped>
.text-style {
  color: white;
  font-family: "Roboto Mono", monospace !important;
  text-shadow: 0 0 5px #ffff, 0 0 10px #ffff;

}

.icon-style-at-footer {
  margin-bottom: 5px;
}
.footer-style {
  color: black;
  font-size: 13px;
  background-color: #04ecdc;
  justify-content: center;
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
