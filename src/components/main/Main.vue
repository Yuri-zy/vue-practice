<template>
  <div class="main">
    <Title></Title>
    <Content></Content>
  </div>
</template>

<script>
import Title from "../title/Title.vue"
import Content from "../content/Content.vue"

export default {
  name: "Main",
  components: {
    Title,
    Content
  }
}
</script>

<style scoped>
</style>