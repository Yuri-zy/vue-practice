<template>
  <div class="content">
    <div class="content-head">
      <type-selector @typeUpdate="typeUpdate"></type-selector>
      <search-box @searchUpdate="searchUpdate"></search-box>
    </div>
    <div class="content-detail">
      <List :selectedType="selectedType" :searchValue="searchValue"></List>
    </div>
  </div>
</template>

<script>
import TypeSelector from "../typeselector/TypeSelector.vue"
import SearchBox from "../searchbox/SearchBox.vue"
import List from "../list/List.vue"

export default {
  name: "Content",
  data() {
    return {
      selectedType: "",
      searchValue: ""
    }
  },
  components: {
    TypeSelector,
    SearchBox,
    List
  },
  methods: {
    typeUpdate(lastType) {
      // console.log(lastType)
      this.selectedType = lastType
    },
    searchUpdate(searchValue) {
      // console.log(searchValue)
      this.searchValue = searchValue
    }
  }
}
</script>

<style scoped>
.content {
  width: 340px;
  height: 570px;
  background-color: rgba(0, 0, 0, 0.5);
}

.content-head {
  display: flex;
  margin-bottom: 6px;
}
</style>