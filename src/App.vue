<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/org.json"> -->
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
  data() {
    return {
      data: null,
    };
  },
  created() {
    fetch(
      '/org.json',
    )
      .then((d) => d.json())
      .then((d) => {
        console.log('fetched data');
        this.data = d;
      });
  },
  methods: {
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
