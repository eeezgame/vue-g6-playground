<template>
  <div>HelloG6</div>
  <div ref="graph$"></div>
</template>

<script>
import { onMounted, ref } from "vue";
import { useMyGraph } from "./useMyGraph.js";

export default {
  name: "HelloG6",
  setup() {
    const graph$ = ref(null);
    let graphInstance = null;
    onMounted(() => {
      const { graph } = useMyGraph(graph$.value);
      graphInstance = graph;
      console.log("graphInstance:", graphInstance);
    });
    return { graph$ };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less"></style>
