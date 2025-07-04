<template>
    <div class="layout">
      <Header />
      <main>
        <slot />
      </main>
      <footer class="footer">
        <p>&copy; 2025 Все права защищены</p>
      </footer>
    </div>
</template>

<script setup>
import Header from '../components/Header.vue'
</script>
  
<style scoped>
.layout {
  width: 100%;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  padding-top: 72px;
}

.footer {
  margin-top: auto;
  background-color: #f3f4f6;
  text-align: center;
}

@media (min-width: 768px) {
 .layout {
  padding: 0;
 }
}
</style>