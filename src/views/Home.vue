<!-- src/views/Home.vue -->
<template>
  <div>
    <h1>Ivy Quiño</h1>
    <p>Program: Bsit-3</p>
    <nav>
      <router-link to="/home">Home</router-link>
      <router-link to="/products">Products</router-link>
    </nav>
    <div class="background">
      <!-- Add background image CSS here -->
    </div>
  </div>
</template>

<style scoped>
.background {
  background-image: url("/path-to-your-image.jpg");
  height: 400px;
  width: 100%;
}
</style>
