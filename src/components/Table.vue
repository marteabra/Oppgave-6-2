<template>
  <ul>
    <li v-for="crypto in cryptos">
      <div class="name">{{ crypto.name }}</div>
      <div class="price">{{ Math.round(crypto.priceUsd) }}</div>
      <div class="cap">{{ Math.round(crypto.marketCapUsd) }}</div>
      <div>{{ Math.round(crypto.vwap24Hr) }}</div>
    </li>
  </ul>
</template>

<script>
export default {
  data() {
    return {
      cryptos: [],
    };
  },

  created() {
    this.fetchData();
  },
  methods: {
    async fetchData() {
      const url = "https://api.coincap.io/v2/assets";
      const response = await fetch(url);
      const { data } = await response.json();
      this.cryptos = data;
    },
  },
};
</script>

<style scoped>
ul li {
  display: flex;
  justify-content: space-between;
  margin: 0 50 0 50;
}

.cap {
  position: relative;
  text-align: right;
}

.price {
  min-width: 300px;
  text-align: right;
}
</style>