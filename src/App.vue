<template>
  <div id="app">
    <!-- <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div> -->
    <router-view />
  </div>
</template>

<style>
#app {
  font-family: "Source Sans Pro", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
body {
  margin: 0;
}
::-webkit-scrollbar {
  height: 6px;
  width: 6px;
  background: rgba(0, 0, 0, 0.2);
}
::-webkit-scrollbar-corner {
  display: none;
}
::-webkit-scrollbar-thumb {
  background: #677073;
}
</style>
