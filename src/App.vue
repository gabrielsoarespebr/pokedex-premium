<script setup>
// import { RouterLink, RouterView } from 'vue-router'
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';
import Main from './components/Main.vue';

</script>



<template>
  <Header title="Pokedex Premium" class="mb-3"></Header>
  <Main></Main>

  <Footer class="mt-3"></Footer>
  <!-- <header>
    <div class="wrapper">

      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView /> -->
</template>



<style scoped>

</style>
