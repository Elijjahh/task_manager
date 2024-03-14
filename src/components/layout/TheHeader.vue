<script setup lang="ts">
import { RouterLink } from 'vue-router';
import { ref } from 'vue';

const menu = ref({ home: 'Главная', tasks: 'Задачи' });
</script>

<template>
  <header>
    <div class="container">
      <div class="header__logo"></div>
      <nav class="header__nav">
        <ul class="header__menu">
          <li v-for="(text, name) in menu" :key="name" class="header__menu-item">
            <RouterLink :to="{ name: name }" class="header__link">{{ text }}</RouterLink>
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>
