<script setup>
import { RouterLink, RouterView } from 'vue-router'
import Header from '../src/components/header.vue'
import Footer from '../src/components/footer.vue'
</script>

<template>
  <Header />
  <RouterView />
  <Footer />
</template>

<style scoped>
* {
  font-family: 'Kanit', sans-serif;
}
</style>
