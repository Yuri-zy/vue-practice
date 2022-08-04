<template>
  <div class="title">
    <span class="icon"></span>
    <div class="word">违规车辆检测</div>
  </div>
</template>

<script>
export default {
  name: "Title"
}
</script>

<style scoped>
.title {
  display: flex;
  width: 340px;
  height: 40px;
  background-color: rgba(0, 0, 0, 0.6);
  /* border-bottom: 10px solid rgba(0, 0, 0, 0.2); */
  margin-bottom: 10px;
  align-items: center;
}

.icon {
  width: 3px;
  height: 18px;
  background-color: #00e4ff;
  margin-left: 15px;
}

.word {
  height: 18px;
  color: #ffffff;
  font-size: 17px;
  margin-left: 5px;
  line-height: 18px;
}
</style>