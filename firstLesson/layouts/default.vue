<!-- Это вообще разъеб. Понятно по названию. 
Это стандартная верстка для проекта. Все, что на писано тут -
будет на всех страницах. А содержимое страниц будет в Slot -->

<template>
  <div>
    <header class="shadow-sm bg-white">
      <nav class="container mx-auto p-4 flex justify-between">
        <NuxtLink to="/" class="font-bold">Nuxt Dojo</NuxtLink>

        <ul class="flex gap-4">
          <li>
            <NuxtLink to="/">Home</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/about">About</NuxtLink>
          </li>
          <li>
            <NuxtLink class="btn" to="/products">Products</NuxtLink>
          </li>
        </ul>
      </nav>
    </header>

    <div class="container mx-auto p-4">
      <slot />
    </div>
  </div>
</template>

<script setup></script>

<style scoped>
* {
  text-decoration: none;
}

.router-link-exact-active {
  color: rgb(58, 219, 120);
}
</style>
