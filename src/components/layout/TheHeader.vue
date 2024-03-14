<script setup lang="ts">
import { RouterLink } from 'vue-router';
import { ref } from 'vue';

const menu = ref({ home: 'Главная', tasks: 'Задачи' });
</script>

<template>
  <header class="header">
    <div class="container header__container">
      <RouterLink :to="{ name: 'home' }" class="header__logo"><span>Vue</span>Manager</RouterLink>
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

<style scoped lang="scss">
.header {
  padding: 12px 0;
  box-shadow: 0px 30px 60px 0px rgba(158, 165, 255, 0.15);
  background: rgb(255, 255, 255);

  &__container {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  &__logo {
    font-family: Poppins;
    font-size: 32px;
    font-weight: 600;
    line-height: 48px;
    color: #000;

    span {
      color: #575dfb;
    }
  }

  &__nav {
  }

  &__menu {
    display: flex;
    align-items: center;
    gap: 30px;
    list-style-type: none;
  }

  &__menu-item {
  }

  &__link {
    position: relative;
    color: #2a303c;
    font-size: 14px;
    font-weight: 400;
    line-height: 24px;
    transition: 0.3s all;
    &:after {
      content: '';
      display: block;
      width: 100%;
      height: 2px;
      background: #6772fe;
      position: absolute;
      bottom: 0px;
      left: 0;
      opacity: 0;
      transition: all 0.3s;
    }
    &:hover {
      color: #6772fe;
      &:after {
        opacity: 1;
        bottom: -5px;
      }
    }
  }
}
</style>
