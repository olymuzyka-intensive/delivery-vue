<script setup>
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";
import Modal from "./components/Modal.vue";
import { store } from './store/index'
// import { ref } from "vue";

// const isOpen = ref(false);
</script>

<template>
  <div class="page-wrapper">
    <!-- <Header @toggleModal="isOpen = !isOpen" /> -->
        <Header @toggleModal="store.toggleModal(true)" />

    <main class="main">
      <router-view></router-view>
    </main>
    <!-- <Modal :isOpen="isOpen" @toggleModal="isOpen = !isOpen" /> -->
        <!-- <Modal :isOpen="store.isOpen" @toggleModal="isOpen = !isOpen" /> -->
      <Modal :isOpen="store.isOpen" @toggleModal="store.toggleModal(false)" />

    <Footer />
  </div>
</template>

<style scoped>
</style>
