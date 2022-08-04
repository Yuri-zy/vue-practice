<template>
  <div class="content">
    <div class="content-head">
      <type-selector @typeUpdate="update"></type-selector>
      <search-box></search-box>
    </div>
    <div class="content-detail">
      <List :selectedType="selectedType"></List>
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
      selectedType: ""
    }
  },
  components: {
    TypeSelector,
    SearchBox,
    List
  },
  methods: {
    update(lastType) {
      // console.log(lastType)
      this.selectedType = lastType
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

.content-detail {
  height: 515px;
  overflow-y: auto;
  overflow-x: hidden;
}

::-webkit-scrollbar {
  width: 2px;
}

::-webkit-scrollbar-thumb {
  width: 2px;
  height: 50px;
  background-color: #2ed6e6;
}

::-webkit-scrollbar-track {
  height: 500px;
  background-color: rgba(255, 255, 255, 0.3);
}
</style>