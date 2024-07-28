<template>
    <div v-if="isLoading" class="spinner-overlay">
      <atom-spinner
        :animation-duration="1000"
        :size="100"
        color="#04ecdc"
        class="atom-spinner-style"
      />
    </div>
  </template>
  
  <script>
  import { AtomSpinner } from "epic-spinners";
  
  export default {
    name: "isLoadingComponent",
    components: {
      AtomSpinner,
    },
    props: {
      isLoading: {
        type: Boolean,
        required: true,
      },
    },
  };
  </script>
  
  <style scoped>
  .spinner-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: rgba(255, 255, 255, 0.1); /* Semi-transparent background */
    z-index: 9999;
  }
  
  .atom-spinner-style {
    z-index: 10000;
  }
  </style>
  