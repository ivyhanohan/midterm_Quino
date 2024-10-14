<!-- src/components/ProductList.vue -->
<template>
  <div>
    <div v-for="(product, index) in products" :key="index">
      <div v-if="editingIndex === index">
        <input v-model="product.name" />
        <input v-model="product.price" />
        <textarea v-model="product.description"></textarea>
        <button @click="saveEdit(index)">Save</button>
      </div>
      <div v-else>
        <h3>{{ product.name }}</h3>
        <p>Price: {{ product.price }}</p>
        <p>{{ product.description }}</p>
        <button @click="editProduct(index)">Edit</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["products"],
  data() {
    return {
      editingIndex: null,
    };
  },
  methods: {
    editProduct(index) {
      this.editingIndex = index;
    },
    saveEdit(index) {
      this.editingIndex = null;
      this.$emit("update-product", index);
    },
  },
};
</script>




