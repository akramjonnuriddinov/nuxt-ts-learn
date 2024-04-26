<script setup lang="ts">
import { type Product } from "~/types"

defineProps<{
  product: Product
}>()
</script>

<template>
  <div class="card">
    <div class="grid grid-cols-2 gap-10">
      <div class="p-7">
        <img :src="product.image" alt="" class="mx-auto my-7 max-w-[400px]" />
      </div>
      <div class="p-7">
        <h2 class="text-4xl my-7">{{ product.title }}</h2>
        <p class="text-xl my-7">Price - ${{ product.price }}</p>
        <span class="block pb-2 mb-4 font-bold border-b-2"
          >Product description:</span
        >
        <p class="mb-7">{{ product.description }}</p>
        <button class="flex btn">
          <i class="mr-2 material-symbols-outlined">add_shopping_cart</i>
          <span>Add to cart</span>
        </button>
      </div>
    </div>
  </div>
</template>
