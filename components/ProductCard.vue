<script setup lang="ts">
import { type Product } from "@/types"

defineProps<{
  product: Product
}>()
</script>

<template>
  <div class="text-center card">
    <img :src="product.image" :alt="product.title" class="thumb" />
    <h3 class="m-4 font-bold text-gray-500 truncate">{{ product.title }}</h3>
    <nuxt-link :to="`/products/${product.id}`" class="block my-4 btn"
      >View Details</nuxt-link
    >
  </div>
</template>

<style scoped>
.thumb {
  max-height: 120px;
  max-width: 70%;
  margin: 0 auto;
}
</style>
