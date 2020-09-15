<template>
  <div class="menu">
    <svg
      class="svg"
      style="width:20px;height:22px;color: #DDEAF1;"
      viewBox="0 0 24 24"
      v-on:click="demoMessage()"
    >
      <path
        fill="currentColor"
        d="M13,9V3.5L18.5,9M6,2C4.89,2 4,2.89 4,4V20A2,2 0 0,0 6,22H18A2,2 0 0,0 20,20V8L14,2H6Z"
      />
    </svg>
    <svg
      class="svg"
      style="width:24px;height:22px;color: #FFA430;"
      viewBox="0 0 24 24"
      v-on:click="demoMessage()"
    >
      <path
        fill="currentColor"
        d="M10,4H4C2.89,4 2,4.89 2,6V18A2,2 0 0,0 4,20H20A2,2 0 0,0 22,18V8C22,6.89 21.1,6 20,6H12L10,4Z"
      />
    </svg>
    <svg
      class="svg"
      style="width:24px;height:22px;color: #31c5f0;"
      viewBox="0 0 24 24"
      v-on:click="demoMessage()"
    >
      <path
        fill="currentColor"
        d="M15,9H5V5H15M12,19A3,3 0 0,1 9,16A3,3 0 0,1 12,13A3,3 0 0,1 15,16A3,3 0 0,1 12,19M17,3H5C3.89,3 3,3.9 3,5V19A2,2 0 0,0 5,21H19A2,2 0 0,0 21,19V7L17,3Z"
      />
    </svg>
    <svg
      class="svg"
      style="width:24px;height:22px;color: #FF4A4C;"
      viewBox="0 0 24 24"
      v-on:click="demoMessage()"
    >
      <path
        fill="currentColor"
        d="M12,15.5A3.5,3.5 0 0,1 8.5,12A3.5,3.5 0 0,1 12,8.5A3.5,3.5 0 0,1 15.5,12A3.5,3.5 0 0,1 12,15.5M19.43,12.97C19.47,12.65 19.5,12.33 19.5,12C19.5,11.67 19.47,11.34 19.43,11L21.54,9.37C21.73,9.22 21.78,8.95 21.66,8.73L19.66,5.27C19.54,5.05 19.27,4.96 19.05,5.05L16.56,6.05C16.04,5.66 15.5,5.32 14.87,5.07L14.5,2.42C14.46,2.18 14.25,2 14,2H10C9.75,2 9.54,2.18 9.5,2.42L9.13,5.07C8.5,5.32 7.96,5.66 7.44,6.05L4.95,5.05C4.73,4.96 4.46,5.05 4.34,5.27L2.34,8.73C2.21,8.95 2.27,9.22 2.46,9.37L4.57,11C4.53,11.34 4.5,11.67 4.5,12C4.5,12.33 4.53,12.65 4.57,12.97L2.46,14.63C2.27,14.78 2.21,15.05 2.34,15.27L4.34,18.73C4.46,18.95 4.73,19.03 4.95,18.95L7.44,17.94C7.96,18.34 8.5,18.68 9.13,18.93L9.5,21.58C9.54,21.82 9.75,22 10,22H14C14.25,22 14.46,21.82 14.5,21.58L14.87,18.93C15.5,18.67 16.04,18.34 16.56,17.94L19.05,18.95C19.27,19.03 19.54,18.95 19.66,18.73L21.66,15.27C21.78,15.05 21.73,14.78 21.54,14.63L19.43,12.97Z"
      />
    </svg>
  </div>
</template>

<script>
export default {
  methods: {
    demoMessage() {
      alert("This feature is not available in the web demo.");
    },
  },
};
</script>
<style scoped>
.menu {
  height: 35px;
  width: 100vw;
  background-color: #3b4248;
}
.svg {
  background-color: #323639;
  padding: 4px 7px;
  margin: 2px;
}
</style>
