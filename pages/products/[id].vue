<script setup lang="ts">
import { type Product } from "@/types"

definePageMeta({
  layout: "products",
})
const { id } = useRoute().params as { id: string }

const { data: product } = await useFetch<Product>(
  `https://fakestoreapi.com/products/${id}`,
  { key: id }
)
</script>

<template>
  <Head>
    <Title>Nuxt Dojo | {{ product?.title }}</Title>
    <Meta name="description" :content="product?.description" />
  </Head>
  <div>
    <product-detail :product="product as Product" />
  </div>
</template>
