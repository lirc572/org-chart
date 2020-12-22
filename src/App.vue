<template>
  <div>
    <tree-chart :data="data" />
  </div>
</template>

<script>
import TreeChart from './components/TreeChart.vue';

export default {
  name: 'App',
  components: {
    TreeChart,
  },
  props: {
    url: {
      type: String,
      default: '',
    },
  },
  data() {
    return {
      data: null,
    };
  },
  watch: {
    url(value) {
      this.updateData(value);
    },
  },
  created() {
    console.log(`VUE_APP_DATA_URL: ${process.env.VUE_APP_DATA_URL}`);
    this.updateData(this.url || process.env.VUE_APP_DATA_URL);
  },
  methods: {
    updateData(url) {
      fetch(url)
        .then((d) => d.json())
        .then((d) => {
          console.log('fetched data');
          this.data = d;
        });
    },
  },
};
</script>
