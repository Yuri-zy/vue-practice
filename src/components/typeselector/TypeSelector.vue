<template>
  <div>
    <select class="select-box" @change="typeSelect" ref="selectbox">
      <option v-for="(type, index) in type" :key="index" :value="type">{{type}}</option>
    </select>
    <!-- {{t}} -->
  </div>
</template>

<script>
import { type } from "@/data/v-data"

export default {
  name: "TypeSelector",
  data() {
    return {
      type: type
    }
  },
  methods: {
    typeSelect() {
      let lastType = this.$refs.selectbox.value
      // console.log(lastType)
      this.$emit("typeUpdate", lastType)
    }
  }
}
</script>

<style scoped>
.select-box {
  width: 100px;
  height: 34px;
  margin: 15px 10px 0 15px;
  background: none;
  color: #a6adb6;
  text-align: center;
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 5px;
  outline: none;
  /* cursor: pointer; */
}
</style>