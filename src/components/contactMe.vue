<template>
  <atom-spinner
    v-if="isLoading"
    :animation-duration="1000"
    :size="60"
    color="#ff1d5e"
  />
  <div class="container">
    <v-form
      class="form-container"
      @submit.prevent="sendEmail"
      ref="form"
      :lazy-validation="lazy"
    >
      <v-row justify="center">
        <v-col cols="12" sm="6">
          <v-text-field
            class="text-field-padding"
            v-model="name"
            :rules="nameRules"
            label="Name"
            name="name"
            solo
            required
          ></v-text-field>

          <v-text-field
            class="text-field-padding"
            v-model="email"
            :rules="emailRules"
            name="email"
            solo
            label="E-mail"
            required
          ></v-text-field>

          <v-text-field
            class="text-field-padding"
            v-model="telephone"
            name="telephone"
            :rules="phoneRules"
            solo
            label="Telephone"
            required
          ></v-text-field>

          <v-text-field
            class="text-field-padding"
            v-model="subject"
            name="subject"
            :rules="textAreaRules"
            label="Subject"
            required
            solo
          ></v-text-field>
        </v-col>

        <v-col cols="12" sm="5">
          <v-textarea
            class="text-field-padding your-message-height"
            name="message"
            v-model="message"
            solo
            :rules="textAreaRules"
            label="Your message"
          />

          <v-btn
            :dark="valid"
            block
            class="submit-email-button"
            @click="sendEmail"
          >
            <span class="submit-button-text"> Submit </span>
          </v-btn>

          <!-- <h1 class="font-weight-light text-style-name display-1">
            Arsen Cenollari
          </h1> -->

          <!-- <h3
            @click="openMap()"
            style="cursor: pointer"
            class="font-weight-light mt-3 text-style font-color"
          >
            Tirane, Albania
          </h3>

          <h3
            @click="writeEmail()"
            style="cursor: pointer"
            class="font-weight-light text-style font-color"
          >
            Email: cenollariarsen7@gmail.com
          </h3> -->
        </v-col>
      </v-row>
    </v-form>
  </div>
</template>

<script>
import { mdiGmail } from "@mdi/js";
import { AtomSpinner } from "epic-spinners";
import emailjs from "emailjs-com"; // BEJME IMPORTIMIN E DUHUR

export default {
  data() {
    return {
      //DEKLAROJME FUSHAT QE NE DUAM DHE NGA KU DO TE MARRIM VLERA
      name: "",
      email: "",
      telephone: "",
      subject: "",
      message: "",
      isLoading: false,
      valid: true,
      //******************************************************************************************************************************//
      //***************** RREGULLA TE VENDOSURA PER PLOTESIMIN E FUSHAVE (SIPAS DESHIRES) *****************//
      nameRules: [
        (v) => !!v || "You must complete your name",
        (v) =>
          (v && v.length >= 5) || "The name must be longer than 6 characters",
      ],
      emailRules: [
        (v) => !!v || "You must complete your e-mail",
        (v) => /.+@.+\..+/.test(v) || "E-mail must be valid",
      ],
      phoneRules: [
        (v) => !!v || "The text field is required",
        (v) => (v && v.length >= 10) || "Minimum 10 characters",
      ],
      textAreaRules: [
        (v) => !!v || "The text field is required",
        (v) => (v && v.length >= 10) || "Minimum 10 characters",
      ],
      lazy: false,
      snackbar: {
        enabled: false,
        text: "",
        color: "",
      },
    };
  },
  methods: {
    openMap() {
      window.open(
        "https://www.google.com/maps/place/Tirana,+Albania/@41.3242769,19.8064902,15z/data=!4m15!1m8!3m7!1s0x1350310470fac5db:0x40092af10653720!2sTirana,+Albania!3b1!8m2!3d41.3275459!4d19.8186982!16zL20vMDdtX2Y!3m5!1s0x1350310470fac5db:0x40092af10653720!8m2!3d41.3275459!4d19.8186982!16zL20vMDdtX2Y?entry=ttu",
        "_blank"
      );
    },

    writeEmail() {
      window.open("mailto:cenollariarsen7@gmail.com");
    },
    emptyFields() {
      this.name = "";
      this.email = "";
      this.telephone = "";
      this.message = "";
      this.subject = "";
      setTimeout(() => {
        this.isLoading = false;
      }, 2000);
    },

    //******************************************************************************************************************************//
    //***************** FUNKSJONI QE DO TE PERDORET PER TE DERGUAR EMAIL-IN *****************//
    sendEmail() {
      this.isLoading = true;
      try {
        emailjs.sendForm(
          "service_u1ay0hb", //VENDOSNI SERVICE ID (QE KENI MBAJTUR SHENIM TEK HAPI I MEPARSHEM)
          "template_09pnylp", // VENDOSNI Template ID (QE KENI MBAJTUR SHENIM TEK HAPI I MEPARSHEM)
          this.$refs.form.$el, // CA TARGETI DO TE KET (FORM)  ref="form"
          "2ydcucD9DD2LytKdw", // VENDOSNI Private Key QE GJENDET TEK PROFILI JUAJ NE MAILJS
          {
            name: this.name,
            email: this.email,
            telephone: this.telephone,
            subject: this.subject,
            message: this.message,
          }
        );
        alert("EMAIL SENT SUCCESSFULLY"); // LAJMEROJE USERIN QE EMAIL U DERGUA
      } catch (err) {
        if (err instanceof ReferenceError) {
          alert("JSON Error: " + err.message);
        } else {
          throw err; // rethrow
        }
      }

      //boshojm pasi te behet send
      this.emptyFields();
    },
  },
};
</script>

<style scoped>
.your-message-height{
  height: 285px;
}
.text-field-padding {
  color: white;
}
.text-style-name {
  font-family: "Russian Dollmaker";
  color: white;
  font-size: 55px;
  font-weight: 100;
}
.text-style {
  color: white;
  font-family: "Roboto Mono", monospace !important;
}

.form-container {
  padding-bottom: 40px;
  padding-top: 40px;
  width: 90%;
}
.container {
  display: flex;
  background-color: #222831;
  justify-content: center;
  align-items: center;
  padding-bottom: 20px;
}
.submit-email-button {
  font-family: "Roboto Mono", monospace !important;
  margin-top: -30px;
  background-color: #04ecdc;
}
.submit-email-button:hover {
  background-color: #04ecdc;
  box-shadow: 0 0 5px #04ecdc, 0 0 10px #04ecdc, 0 0 20px #04ecdc,
    0 0 20px #04ecdc;
}

.submit-email-button:hover .submit-button-text {
  text-shadow: 0 0 5px #04ecdc, 0 0 10px #04ecdc, 0 0 20px #04ecdc,
    0 0 20px #04ecdc;
}
</style>
