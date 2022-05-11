<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
  <!-- <HelloWorld msg="Hello Vue 3 in CodeSandbox!" /> -->
  <gods></gods>
</template>

<script>
// import HelloWorldVue from "./components/HelloWorld.vue";
import godsvue from "./components/godsvue.vue";
export default {
  name: "App",
  components: {
    // HelloWorld: HelloWorldVue,
    gods: godsvue,
  },
  data() {
    return {};
  },
};
</script>

<style>
html {
  background-color: #071425;
  font-size: 10px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #fff;
  margin-top: 60px;
  font-size: 1.4rem;
}
</style>
