<template>
  <div class="list-content">
    <div class="list" v-for="(data, index) in filterType" :key="index">
      <!-- <div class="list" v-for="(data, index) in vData" :key="index"> -->
      <div class="list-head">
        <div class="type" :style="typeColor(data.type)">{{data.type}}</div>
        <div class="car-id">{{data.carID}}</div>
        <div class="desc">{{data.desc}}</div>
      </div>
      <div class="list-detail">
        <div class="pos-detail">
          <span>P</span>
          <div class="pos">{{data.pos}}</div>
        </div>
        <div class="date">{{data.date}}</div>
      </div>
    </div>
  </div>
</template>

<script>
import { type } from "@/data/v-data"
import vData from "@/data/v-data"

// console.log(type)
// console.log(vData)

export default {
  name: "List",
  props: {
    selectedType: ""
  },
  data() {
    return {
      type: type,
      vData: vData
    }
  },
  computed: {
    filterType() {
      if (this.selectedType !== this.type[0]) {
        return this.vData.filter(item => item.type.includes(this.selectedType))
      } else {
        return this.vData
      }
    }
  },
  methods: {
    typeColor(type) {
      //   console.log(type === this.type[1])
      if (type === this.type[1]) {
        return { color: "#f3af4f" }
      } else if (type === this.type[2]) {
        return { color: "#eb524d" }
      } else if (type === this.type[3]) {
        return { color: "#b85ee4" }
      }
    }
  }
}
</script>

<style scoped>
.list {
  width: 310px;
  height: 60px;
  color: #e8e8e8;
  margin-left: 15px;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

.list-head {
  display: flex;
  height: 18px;
  margin-top: 6px;
  font-size: 16px;
  line-height: 18px;
}

.list-head .type {
  margin-left: 5px;
  color: #f4b152;
}

.list-head .car-id {
  margin-left: 5px;
}

.list-head .desc {
  margin-left: 5px;
}

.list-detail {
  display: flex;
  justify-content: space-between;
  height: 20px;
  margin-left: 5px;
  margin-top: 8px;
  color: #a3adb7;
  font-size: 10px;
  line-height: 20px;
}

.list-detail .pos-detail {
  display: flex;
}
.list-detail span {
  width: 14px;
  height: 14px;
}

/* .list-detail .date {
  margin-right: 15px;
} */
</style>