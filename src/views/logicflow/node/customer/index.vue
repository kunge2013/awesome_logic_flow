<template>
  <div class="container" ref="container"></div>
</template>

<script>
  import LogicFlow from "@logicflow/core";
  import "@logicflow/core/lib/style/index.css";
  import data from './CustomData.js';
  import {CustomRectNode} from './CustomRectNode.js';


  export default {
    name: 'lf-Demo',
    data() {
      return {
        renderData: {
          // 节点数据
          nodes: data,
          // 边数据
          edges: [
            {
              id: 'rect-2-circle', // 边ID，性质与节点ID一样
              type: 'polyline', // 边类型
              sourceNodeId: '50', // 起始节点Id
              targetNodeId: '21', // 目标节点Id
            },
          ],
        }
      }
    },
    mounted() {
      this.lf = new LogicFlow({
        container: this.$refs.container,
        grid: true,
      });
      this.lf.render(this.renderData);
    },
  };
</script>

<style scoped>
  .container {
    width: 80%;
    height: 800px;
  }
</style>