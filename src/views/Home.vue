<template>
  <div class="home">
    <Menu />
    <ToolBox />
    <CenterPanel />
    <BottomPanel />
    <RightPanel />
  </div>
</template>

<script>
// @ is an alias to /src
import ToolBox from "@/components/ToolBox.vue";
import CenterPanel from "@//components/CenterPanel.vue";
import Menu from "@//components/Menu.vue";
import RightPanel from "@//components/RightPanel.vue";
import BottomPanel from "@//components/BottomPanel.vue";

export default {
  name: "Home",
  components: {
    ToolBox,
    CenterPanel,
    Menu,
    RightPanel,
    BottomPanel,
  },
};
</script>
<style scoped>
.home {
  height: 100vh;
  width: 100vw;
  background: radial-gradient(#262a2d, #212527);
}
</style>
