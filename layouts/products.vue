<script setup lang="ts"></script>

<template>
  <header class="bg-white shadow-sm">
    <div class="container flex justify-between p-4 mx-auto">
      <nuxt-link to="/" class="font-bold">Dojo</nuxt-link>
      <ul class="flex gap-4">
        <li>
          <nuxt-link to="/">Home</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/about">About</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/products" class="">Products</nuxt-link>
        </li>
      </ul>
    </div>
  </header>

  <div class="container p-4 mx-auto">
    <slot />
  </div>

  <footer class="border-t-2">
    <div class="container flex justify-between p-4 mx-auto">
      <ul class="flex gap-4">
        <li>
          <nuxt-link to="/">Home</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/about">About</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/products">Products</nuxt-link>
        </li>
      </ul>
    </div>
  </footer>
</template>

<style scoped>
.router-link-exact-active {
  color: #07aa87;
}
</style>
