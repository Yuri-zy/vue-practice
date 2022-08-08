<template>
  <div class="search-box">
    <input type="search" class="search" placeholder="搜索车牌号…" @keyup.enter="searchUpdate" ref="searchbox">
  </div>
</template>

<script>
export default {
  name: "SearchBox",
  methods: {
    searchUpdate() {
      let searchValue = this.$refs.searchbox.value
      // console.log(searchValue)
      this.$emit("searchUpdate", searchValue)
    }
  }
}
</script>

<style scoped>
.search-box {
  display: flex;
}

.search {
  width: 200px;
  height: 34px;
  margin-top: 15px;
  background: none;
  border: 1px solid rgba(255, 255, 255, 0.2);
  outline: none;
  border-radius: 5px;
  padding-left: 5px;
  color: #a6adb6;
}

input::-webkit-search-cancel-button {
  display: none;
}
</style>