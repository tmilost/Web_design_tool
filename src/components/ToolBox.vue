<template>
  <div class="toolBox">
    <div class="toolboxSize">
      <el-card class="box-card">
        <div slot="header" class="clearfix">
          <span>ToolBox</span>
          <el-button style="float: right; padding: 3px 4px 3px 4px" size="mini"
            >X</el-button
          >
        </div>
        <div class="search">
          <el-input placeholder="Filter keyword" v-model="filterText">
          </el-input>
        </div>
        <div class="tree">
          <el-tree
          empty-text="No component were found"
            class="filter-tree"
            :data="components"
            :props="defaultProps"
            default-expand-all
            :filter-node-method="filterNode"
            ref="tree2"
          >
          </el-tree>
        </div>
      </el-card>
    </div>
  </div>
</template>

<script>
export default {
  watch: {
    filterText(val) {
      this.$refs.tree2.filter(val);
    },
  },

  methods: {
    filterNode(value, data) {
      if (!value) return true;
      return data.label.indexOf(value) !== -1;
    },
  },
  data: function() {
    return {
       filterText: '',
      components: [
        {
          label: "Controls",
          children: [
            {
              label: "Button",
            },
              {
              label: "Split Button",
            },
            {
              label: "Button Group",
            },
            {
              label: "Button Toolbar",
            },
            {
              label: "Dropdown",
            },
             {
              label: "Link",
            },
          ],
        },
        {
          label: "Level one 2",
          children: [
            {
              label: "Level two 2-1",
            },
          ],
        },
        {
          label: "Level one 3",
          children: [
            {
              label: "Level two 3-1",
            },
          ],
        },
      ],
    };
  },
  // props: {
  //   msg: String
  // }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.toolboxSize {
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
  clear: both;
}

.box-card {
  width: 220px;
}
.tree{
  margin-top: 25px;
}
</style>
