<template>
    <div class="layout">
      <Header />
      <main class="main">
        <slot />
      </main>
      <Footer />
    </div>
</template>

<script setup lang="ts">
import Header from '../components/Header.vue';
import Footer from '../components/Footer.vue';
</script>
  
<style scoped>
.layout {
  width: 100%;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  padding-top: 72px;
}

.main {
  max-width: 1440px;
  margin: 0 auto;
}

@media (min-width: 768px) {
  .layout {
    padding-top: 64px;
  }
}

@media (min-width: 992px) {
 .layout {
  padding: 0;
 }
}
</style>