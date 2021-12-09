<template>
  <div id="app">
    <Header />
    <router-view />
  </div>
</template>

<script>
import Header from "./components/Header.vue";

export default {
  name: "App",
  components: {
    Header,
  },
};
</script>

<style lang="scss">
html,body {
    margin: 0;
    padding: 0;
   height: 100%;
 }
  #app {
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;
    min-width: 720px;
    min-height: 100%;
  }
</style>
