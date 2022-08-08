<template>
  <div class="list-content">
    <transition-group name="list" tag="div">
      <div class="list" v-for="(data, index) in filterData" :key="index" :class="{active: currentIndex===index}" @click="listClick(index)">
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
    </transition-group>
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
    selectedType: "",
    searchValue: ""
  },
  data() {
    return {
      type: type,
      vData: vData,
      currentIndex: -1
    }
  },
  computed: {
    filterData() {
      if (this.selectedType !== this.type[0]) {
        return this.vData.filter(item => item.type.includes(this.selectedType))
      } else if (this.searchValue) {
        return this.vData.filter(item => item.carID.indexOf(this.searchValue) !== -1)
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
    },
    listClick(index) {
      // console.log(index)
      // this.currentIndex = index
      if (this.currentIndex !== index) {
        this.currentIndex = index
      } else {
        this.currentIndex = -1
      }
    }
  }
}
</script>

<style scoped>
.list-content {
  height: 515px;
  overflow-y: auto;
  overflow-x: hidden;
}

::-webkit-scrollbar {
  width: 2px;
}

::-webkit-scrollbar-thumb {
  width: 2px;
  /* height: 50px; */
  background-color: #2ed6e6;
}

::-webkit-scrollbar-track {
  height: 500px;
  background-color: rgba(255, 255, 255, 0.3);
}

.list {
  width: 310px;
  height: 60px;
  color: #e8e8e8;
  margin-left: 15px;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
  cursor: pointer;
}

.list:hover {
  background-color: rgba(255, 255, 255, 0.1);
}

.list-head {
  display: flex;
  height: 18px;
  padding-top: 6px;
  font-size: 14px;
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

.list-detail .date {
  margin-right: 5px;
}

.active {
  background-color: rgba(255, 255, 255, 0.1);
}

.list-enter-active {
  transition: all 0.3s ease;
}
.list-leave-active {
  transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}
.list-enter,
.list-leave-to {
  transform: translateX(10px);
  opacity: 0;
}
</style>