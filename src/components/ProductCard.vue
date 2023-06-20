<template>
  <div class="card">
    <div class="card-title">
      {{ product.name }}
    </div>
    <div class="card-body">
      <i class="icofont-10x icofont-{{product.icon}} icofont-raddish"></i>
      <form>
        <div class="row">
          <div class="cell">
            <label>Type:</label>
          </div>
          <div class="cell">
            <em>{{ product.type }}</em>
          </div>
        </div>
        <div class="row">
          <div class="cell">
            <label>Price:</label>
          </div>
          <div class="cell">${{ product.price.USD }}</div>
        </div>
        <div class="row">
          <div class="cell">
            <label>Quantity:</label>
          </div>
          <div class="cell">
            <input type="number" v-model.number="quantity" />
          </div>
        </div>
      </form>
    </div>
    <div class="card-footer">
      <button
        @click="addToCart(product.name, index, quantity)"
        class="btn btn-light"
      >
        Add to cart
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductCard",
  props: ["product", "index", "addToCart"],
  data() {
    return {
      quantity: 0,
    };
  },
  computed: {},
  methods: {
    // getPrice(name) {
    //   const product = this.inventory.find((p) => {
    //     return p.name === name;
    //   });
    //   return product.price.USD;
    // },
    // calculateTotal() {
    //   const total = Object.entries(this.cart).reduce((acc, curr) => {
    //     return acc + curr[1] * this.getPrice(curr[0]);
    //   }, 0);
    //   return total.toFixed(2);
    // },
  },
};
</script>

<style scoped></style>
