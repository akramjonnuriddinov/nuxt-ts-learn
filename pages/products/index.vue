<script setup lang="ts">
import { type Product } from "@/types"

definePageMeta({
  layout: "products",
})

useHead({
  title: "Dojo Nuxt | Merch",
  meta: [{ name: "description", content: "Nuxt Merch Page" }],
})

const products = ref<Product[]>()
const isLoading = ref<Boolean>(true)

async function fetchData(url: string): Promise<Product[]> {
  try {
    const response = await fetch(url)
    if (!response.ok) {
      throw new Error("Network was not OK")
    }
    const data = await response.json()
    return data as Product[]
  } catch (error) {
    console.error("Error fetching data: ", error)
    return []
  }
}
async function fetchProducts() {
  try {
    isLoading.value = true
    products.value = await fetchData("https://fakestoreapi.com/products")
  } catch (error) {
    console.error("Error fetching data: ", error)
  } finally {
    isLoading.value = false
  }
}
fetchProducts()
</script>

<template>
  <div v-if="isLoading">Loading...</div>
  <div v-else class="grid grid-cols-4 gap-5">
    <div v-for="product in products">
      <product-card :product="product" />
    </div>
  </div>
</template>
