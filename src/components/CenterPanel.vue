<template>
  <div class="panel" >
    <div class="tool-bar">
      <el-button
        icon="el-icon-search"
        circle
        v-on:click="caculateZoomUp()"
      ></el-button>
      <el-button icon="el-icon-search" circle  v-on:click="caculateZoomDown()"></el-button>
      {{ zoomChange }}
    </div>
    <div class="mainCanvas">
    <div class="canvas" >
        <div :style="zoomChange1">
      asdasdasdasd asd asd asd asd asd asd asd asd asd asd asdasdasdasda sd asd
      asd asd asd

      <img src="@/assets/logo.png" alt="Italian Trulli" />
      </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      zoomPercent: [
        "0%",
        "25%",
        "50%",
        "75%",
        "100%",
        "125%",
        "150%",
        "175%",
        "200%",
      ],
      zoomStyle: [
        "transform:scale(1.0,1.0)",
        "transform:scale(0.25,0.25)",
        "transform:scale(0.5,0.5)",
        "transform:scale(0.75,0.75)",
        "transform:scale(1.0,1.0)",
        "transform:scale(1.25,1.25)",
        "transform:scale(1.5,1.5)",
        "transform:scale(1.75,1.75)",
        "transform:scale(2.0,2.0)",
      ],
      zoomChangeValue: 4,
    };
  },
  methods: {
    caculateZoomUp() {
      if (this.zoomChangeValue < 8) {
        ++this.zoomChangeValue;
      }
    },
    caculateZoomDown() {
      if (this.zoomChangeValue > 1) {
        --this.zoomChangeValue;
      }
    },
  },
  computed: {
    zoomChange() {
      return this.zoomPercent[this.zoomChangeValue];
    },
    zoomChange1() {
      return this.zoomStyle[this.zoomChangeValue];
    },
  },
};
</script>

<style scoped>
.panel {
  margin: auto;
  width: 50%;
  height: 50%;
  border: 15px, darkblue;
  border-style: dashed;
}
.tool-bar {
}
.mainCanvas{
    background-color: aqua;
     width: 100%;
  height: 100%;
}
.canvas {
  margin: 5% 10% 5% 10%;
  padding: 150px;
  overflow: scroll;
  width: 200px;
  height: 10px;
}
</style>
