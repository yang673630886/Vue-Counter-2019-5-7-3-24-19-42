<template>
  <div>
    <span>{{index}}:</span>
    <button v-on:click="add">+</button>
    <span>{{number1}}</span>
    <button v-on:click="minus">-</button>
  </div>
</template>

<script>
export default {
  props: {
    index: Number,
    str: String
  },
  data() {
    return {
      number1: this.index
    };
  },
  watch:{
      num:{
         init()
      }
  },
  methods: {
    add: function() {
      this.number1++;
      this.$emit("update", 1);
    },
    minus: function() {
      this.number1--;
      this.$emit("update", -1);
    },
    init: function(str) {
      window.console.log("aaa");
      this.str = str;
      this.number1 = this.index;
    }
  }
};
</script>