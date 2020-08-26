<template>
  <div class="toolBox">
    <div class="toolboxSize">


<el-card class="box-card">
  <div slot="header" class="clearfix">
    <span>ToolBox</span>
        <el-button style="float: right; padding: 3px 4px 3px 4px"  size="mini">X</el-button>
  </div>
  <div v-for="o in 4" :key="o" class="text item">
    {{'List item ' + o }}
  </div>
</el-card>

    </div>

  </div>
</template>

<script>
export default {
  // name: 'HelloWorld',
  // props: {
  //   msg: String
  // }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.toolboxSize{
  width: 1250px;
  align-items: left;
}
.text {
    font-size: 14px;
  }

  .item {
    margin-bottom: 18px;
  }

  .clearfix:before,
  .clearfix:after {
    display: table;
    content: "";
  }
  .clearfix:after {
    clear: both
  }

  .box-card {
    width: 220px;
  }
</style>
