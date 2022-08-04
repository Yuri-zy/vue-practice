<template>
  <div>
    <input type="search" class="search" placeholder="搜索车牌号…">
  </div>
</template>

<script>
export default {
  name: "SearchBox"
}
</script>

<style scoped>
.search {
  width: 200px;
  height: 34px;
  margin-top: 15px;
  background: none;
  border: 1px solid rgba(255, 255, 255, 0.2);
  outline: none;
  border-radius: 5px;
}
</style>