<!-- src/components/ProductForm.vue -->
<template>
  <form @submit.prevent="submitForm">
    <label>Product Name:</label>
    <input type="text" v-model="productName" required />

    <label>Price:</label>
    <input type="number" v-model="price" required />

    <label>Description:</label>
    <textarea v-model="description" required></textarea>

    <button type="submit">Add Product</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      productName: "",
      price: "",
      description: "",
    };
  },
  methods: {
    submitForm() {
      const product = {
        name: this.productName,
        price: this.price,
        description: this.description,
      };
      this.$emit("add-product", product);
      this.productName = "";
      this.price = "";
      this.description = "";
    },
  },
};
</script>
