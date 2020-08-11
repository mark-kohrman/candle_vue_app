<template>
  <div class="candles-index">
    <h1>All Candles</h1>
    <div v-for="candle in candles">
      <h2> {{candle.scent}}</h2>
      <p>Color: {{candle.color}}</p>
      <p>Price: {{candle.price}}</p>

    </div>


  </div>
</template>

<style>
</style>

<script>
import axios from "axios";

export default {
  data: function () {
    return {
      candles: [],
    };
  },
  created: function () {
    axios.get("/api/candles").then((response) => {
      console.log("candles index", response);
      this.candles = response.data;
    });
  },
  methods: {},
};
</script>