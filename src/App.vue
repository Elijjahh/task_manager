<script setup lang="ts">
import { RouterView } from 'vue-router';
import TheHeader from './components/layout/TheHeader.vue';
</script>

<template>
  <TheHeader />
  <main>
    <RouterView />
  </main>
</template>
