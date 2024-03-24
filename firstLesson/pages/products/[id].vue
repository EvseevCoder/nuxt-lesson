<!-- /test/:id - т.е. прописываем все, что угодно 
  и код это считывает в переменную id -->

<template>
  <div>
    <ProductDeteils :product="product" />
  </div>
</template>

<script setup>
const { id } = useRoute().params;

const uri = "https://fakestoreapi.com/products/" + id;

// Необходимо прокидывать option - key для избежания бага с кешируемым запросом
const { data: product } = await useFetch(uri, { key: id });

if (!product.value) {
  throw createError({
    status: 404,
    statusMessage: "product is not define",
    fatal: true,
  });
}

definePageMeta({
  layout: "products",
});

console.log();

useHead({ title: `${product.value.title}` });
</script>

<style scoped></style>
