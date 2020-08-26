<template>
  <div class="home">
   
    <ToolBox />
        <!-- <ToolBox msg="Welcome to Your Vue.js App"/> -->
  </div>
</template>

<script>
// @ is an alias to /src
import ToolBox from '@/components/ToolBox.vue'

export default {
  name: 'Home',
  components: {
    ToolBox
  }
}
</script>
