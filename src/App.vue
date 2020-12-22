<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/org.json"> -->
    <tree-chart :data="data" />
  </div>
</template>

<script>
import TreeChart from './components/TreeChart.vue';
import orgData from './assets/org.json';

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
    // fetch(
    //   'https://gist.githubusercontent.com/bumbeishvili/dc0d47bc95ef359fdc75b63cd65edaf2/raw/c33a3a1ef4ba927e3e92b81600c8c6ada345c64b/orgChart.json',
    // )
    //   .then((d) => d.json())
    //   .then((d) => {
    //     console.log('fetched data: ', d.length);
    //     this.data = d;
    //   });
    this.data = orgData;
  },
  methods: {
    setData() {
      this.data = orgData;
    },
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
