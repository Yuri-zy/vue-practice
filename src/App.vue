<template>
  <div id="app">
    <Main></Main>
  </div>
</template>

<script>
import Main from "./components/main/Main.vue"

export default {
  name: "App",
  components: {
    Main
  }
}
</script>

<style>
body {
  margin: 0;
  padding: 0;
  background: url("./assets/img/background.jpg");
}
#app {
  width: 350px;
  height: 630px;
  background-color: rgba(0, 0, 0, 0.2);
  margin-top: 20px;
  margin-left: 10px;
}
</style>
