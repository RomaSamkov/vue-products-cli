<template>
  <div class="about">
    <main class="wrapper">
      <h1>Products</h1>

      <div class="card-container">
        <ProductCard
          v-for="(product, index) in inventory.slice(0, 3)"
          :key="product.id"
          :index="index"
          :product="product"
          :addToCart="addToCart"
          class="card"
        />
      </div>
    </main>
  </div>
</template>

<script>
import ProductCard from "@/components/ProductCard.vue";

export default {
  name: "ProductsView",
  props: ["inventory", "addToCart"],
  components: { ProductCard },
};
</script>
