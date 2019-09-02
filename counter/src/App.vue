<template>
  <div id="app">
    <input v-model="num" @input="initData" />
    <Test v-for=" n in parseInt(num)" v-bind:key="n" v-bind:index="n" v-on:update="sumAll"></Test>
    <p>{{sumInit}}</p>
  </div>
</template>
<script>
import Test from "./components/Test.vue";

export default {
  name: "app",
  components: {
    // HelloWorld,
    Test
  },
  data() {
    return {
      num: 0,
      sumInit: 0
    };
  },

  methods: {
    sumAll: function(a) {
      this.sumInit += a;
    },
    initData: function() {
      this.sumInit = ((1 + parseInt(this.num)) * parseInt(this.num)) / 2;
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
