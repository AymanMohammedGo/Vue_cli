<template>
  <div>
    <H1>Products</H1>
    <ul v-for="(product, i) in products" :key="i">
      <li><strong>ID:</strong> {{ product.id }}</li>
      <li><strong>Title:</strong> {{ product.title }}</li>
      <li><strong>Category:</strong> {{ product.category }}</li>
      <hr />
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      products: [],
    };
  },
  methods: {
    async getData() {
      await fetch("https://dummyjson.com/products")
        .then((res) => res.json())
        .then((data) => (this.products = data.products));
    },
  },
  async mounted() {
    await this.getData();
  },
};
</script>
