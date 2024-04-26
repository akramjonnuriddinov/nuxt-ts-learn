<script setup lang="ts">
const { id } = useRoute().params
import { type Product } from "@/types"

definePageMeta({
  layout: "products",
})

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
const product = ref()
async function fetchProductById() {
  product.value = (
    await useFetch(`https://fakestoreapi.com/products/${id}`)
  ).data
}
fetchProductById()
</script>

<template>
  <div>Product details for {{ id }} and {{ product }}</div>
</template>
