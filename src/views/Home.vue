<template>
  <Header />

  <div class="table__header">
    <div>CRYPTO</div>
    <div>PRICE</div>
    <div>MARKED CAP</div>
    <div>24H</div>
  </div>
  <hr />
  <Table />
  <Footer />
</template>

<script>
import Header from "../components/Header.vue";
import Footer from "../components/Footer.vue";
import Table from "../components/Table.vue";

export default {
  components: {
    Header,
    Footer,
    Table,
  },

  data() {
    clientID: import.meta.env.VITE_APP_NAME;
  },
};
</script>

<style scoped>
.table__header {
  display: flex;
  justify-content: space-between;
  margin: 150 50 0 50;
}

hr {
  border: 1px solid black;
  margin: 0 50 0 50;
}
</style>