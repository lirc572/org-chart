<template>
  <div ref="svgElementContainer"></div>
</template>

<script>
import TreeChart from 'd3-org-chart';

export default {
  name: 'Chart',
  props: ['data'],
  data() {
    return {
      chartReference: null,
    };
  },
  watch: {
    data(value) {
      this.renderChart(value);
    },
  },
  mounted() {
    if (this.data) {
      this.renderChart(this.data);
    }
  },
  methods: {
    renderChart(data) {
      console.log('renderChart');
      if (!this.chartReference) {
        this.chartReference = new TreeChart();
      }
      this.chartReference
        .container(this.$refs.svgElementContainer) // node or css selector
        .data(data)
        .svgWidth(500)
        .initialZoom(0.4)
        .onNodeClick((d) => console.log(`${d} node clicked`))
        .render();
    },
  },
};
</script>
