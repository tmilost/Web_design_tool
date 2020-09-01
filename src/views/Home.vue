<template>
  <div class="home">
   
    <ToolBox />
    <CenterPanel/>
        <!-- <ToolBox msg="Welcome to Your Vue.js App"/> -->
  </div>
</template>

<script>
// @ is an alias to /src
import ToolBox from '@/components/ToolBox.vue'
import CenterPanel from '@//components/CenterPanel.vue'

export default {
  name: 'Home',
  components: {
    ToolBox,
    CenterPanel
  }
}
</script>
