<template>
  <div class="panel" v-on:drop="drop" v-on:dragover="allowDrop">
    <div class="tool-bar">
      <svg
        style="width:24px;height:24px;color: #fff;"
        viewBox="0 0 24 24"
        v-on:click="caculateZoomUp()"
      >
        <path
          fill="currentColor"
          d="M15.5,14L20.5,19L19,20.5L14,15.5V14.71L13.73,14.43C12.59,15.41 11.11,16 9.5,16A6.5,6.5 0 0,1 3,9.5A6.5,6.5 0 0,1 9.5,3A6.5,6.5 0 0,1 16,9.5C16,11.11 15.41,12.59 14.43,13.73L14.71,14H15.5M9.5,14C12,14 14,12 14,9.5C14,7 12,5 9.5,5C7,5 5,7 5,9.5C5,12 7,14 9.5,14M12,10H10V12H9V10H7V9H9V7H10V9H12V10Z"
        />
      </svg>

      <svg
        style="width:24px;height:24px;color: #fff;"
        viewBox="0 0 24 24"
        v-on:click="caculateZoomDown()"
      >
        <path
          fill="currentColor"
          d="M15.5,14H14.71L14.43,13.73C15.41,12.59 16,11.11 16,9.5A6.5,6.5 0 0,0 9.5,3A6.5,6.5 0 0,0 3,9.5A6.5,6.5 0 0,0 9.5,16C11.11,16 12.59,15.41 13.73,14.43L14,14.71V15.5L19,20.5L20.5,19L15.5,14M9.5,14C7,14 5,12 5,9.5C5,7 7,5 9.5,5C12,5 14,7 14,9.5C14,12 12,14 9.5,14M7,9H12V10H7V9Z"
        />
      </svg>
      <el-dropdown>
        <span class="el-dropdown-link">
          {{ changeString(deviceSizeValue) }}
          <i class="el-icon-arrow-down el-icon--right"></i>
        </span>
        <el-dropdown-menu slot="dropdown">
          <div
            v-for="a in deviceNames"
            v-bind:key="a"
            v-on:click="changeCanvasSize(a)"
          >
            <el-dropdown-item>{{ a }}</el-dropdown-item>
          </div>
        </el-dropdown-menu>
      </el-dropdown>
      <p>@</p>
      <p>{{ zoomChange }}</p>
    </div>
    <div class="mainCanvas">
      <div class="canvas" :style="deviceSizeValue">
        <div :style="zoomChange1">
          asdasdasdasd asd asd asd asd asd asd asd asd asd asd asdasdasdasda sd
          asd asd asd asd

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
      devicesSize: [
        "width:412px;height:892px;",
        "width:360px;height:760px",
        "width:360px;height:780px",
        "width:412px;height:824px",
        "width:412px;height:847px",
        "width:375px;height:812px",
        "width:375px;height:667px",
        "width:414px;height:736px",
        "width:1024px;height:1366px",
        "width:768px;height:1024px",
        "width:1280px;height:900px",
        "width:1280px;height:800px",
        "width:1280px;height:800px",
        "width:1440px;height:900px",
        "width:1368px;height:912px",
        "width:1280px;height:850px",
        "width:1366px;height:768px",
        "width:1440px;height:900px",
        "width:1600px;height:900px",
        "width:1920px;height:1080px",
      ],
      deviceNames: [
        "OnePlus 7",
        "Galaxy S10",
        "LG G8",
        "Google Pixel 3",
        "Google Pixel 3 XL",
        "iPhone XS",
        "iPhone 8",
        "iPhone 8 plus",
        "iPad Pro",
        "iPad Air",
        "Google Pixel C",
        "MacBook Air",
        'MacBook 13"',
        'MacBook 15"',
        "Microsoft Surface Pro",
        "ChromeBook Pixel",
        "Desktop HD",
        "Desktop WXGA+",
        "Desktop HD+",
        "Desktop FHD+",
      ],
      zoomChangeValue: 4,
      deviceSizeValue: "width:360px;height:412px;",
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
    allowDrop(ev) {
      ev.preventDefault();
    },

    drag(ev) {
      ev.dataTransfer.setData("text", ev.target.id);
    },

    drop(ev) {
      ev.preventDefault();
      var data = ev.dataTransfer.getData("text");
      ev.target.appendChild(document.getElementById(data));
    },
    changeCanvasSize(deviceName) {
      this.deviceSizeValue = this.devicesSize[
        this.deviceNames.indexOf(deviceName)
      ];
    },
    changeString(str) {
      var i = str.indexOf(";");
      str = str.split("");

      str[i] = " x ";
      var c = str.indexOf(";");
      str[c] = "  ";
      str = str.join("");
      return str;
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
  width: calc(100vw - 481px);
  height: calc(100vh - 37px);
  background: radial-gradient(#262a2d, #212527);
  float: left;
  padding-top: 2px;
}
.mainCanvas {
  max-width: 500px;
  max-height: 500px;
  overflow: scroll;
}
.canvas {
  margin: 5% 10% 5% 10%;
  overflow: scroll;
  background-color: antiquewhite;
}
.tool-bar {
  background: #4d575f;
  height: 35px;
}
svg {
  padding: 1px;
  margin: 5px;
  float: left;
}
svg:hover {
  background: linear-gradient(#33383c, #2f3438);
}
.el-dropdown {
  color: #fff;
  padding: 1px;
  margin: 7px;
  float: left;
}
p {
  float: left;
  padding: 1px;
  margin: 9px 0px 9px 0px;
  color: #fff;
  font-size: 12px;
}
</style>
