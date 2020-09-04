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
        <!-- sadasdasd -->
        <button id="drag1" draggable="true" v-on:dragstart="drag" type="button">
          Drag me!
        </button>
        <div class="tree">
          <el-tree
            empty-text="No component were found"
            class="filter-tree"
            :data="components"
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
  },
  data: function() {
    return {
      filterText: "",
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
.toolBox {
  height: calc(100vh - 37px);
  float: left;
  margin-top: 2px;
  padding-right: 2px;
  /* saved this for later */
  /* background: radial-gradient(#262a2d, #212527); */
  background-color: #2c3134;
}
.toolboxSize {
  width: 250px;

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

.tree {
  margin-top: 25px;
}
</style>
