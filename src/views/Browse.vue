<template>
  <div>
    <div class="pure-menu pure-menu-horizontal">
      <ul class="pure-menu-list">
        <li class="pure-menu-item">
          <a @click="select('Human')" href="#" class="pure-menu-link">Human</a>
        </li>
        <li class="pure-menu-item">
          <a @click="select('Plant')" href="#" class="pure-menu-link">Plant</a>
        </li>
        <li class="pure-menu-item">
          <a @click="select('Animal')" href="#" class="pure-menu-link"
            >Animal</a
          >
        </li>
        <li class="pure-menu-item">
          <a @click="select('Other')" href="#" class="pure-menu-link">Other</a>
        </li>
      </ul>
    </div>
    <ProductList :products="products" />
  </div>
</template>

<script>
import ProductList from "../components/ProductList.vue";
export default {
  name: "Browse",
  components: {
    ProductList,
  },
  data() {
    return {
      country: "",
    };
  },
  computed: {
    products() {
      return this.$root.$data.products.filter(
        (product) => product.country === this.country
      );
    },
  },
  methods: {
    select(country) {
      this.country = country;
    },
  },
};
</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}
.search {
  border: 1px solid #ccc;
  border-radius: 4px;
  width: 50%;
}
form {
  display: table;
  width: 100%;
}
i {
  display: table-cell;
  padding-left: 10px;
  width: 1px;
}
input {
  display: table-cell;
  font-size: 20px;
  border: none !important;
  box-shadow: none !important;
  width: 100%;
  height: 40px;
}
</style>
