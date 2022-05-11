<template>
  <div>
    <MyComponent></MyComponent>
    <!-- <RegisterForms></RegisterForms> -->
  </div>
</template>

<script>
import MyComponent from "./components/MyComponent.vue";
// import RegisterForms from "./components/RegisterForms.vue";

export default {
  name: "App",
  components: {
    MyComponent,
    // RegisterForms,
  },
};
</script>

<style>
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
</style>
