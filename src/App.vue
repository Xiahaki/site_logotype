<template>
  <div id="app">
    <AppHeader />
    <HomePage />
  </div>
</template>
<script setup lang="ts">
import AppHeader from '@/components/AppHeader.vue'
import HomePage from '@/views/HomePage.vue'
</script>
<style>
#app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}
</style>
