<template>
    <div class="partner-card">
      <img :src="logo" alt="Partner Logo" class="logo" />
    </div>
</template>
  
<script setup lang="ts">
defineProps<{
    logo: string
}>()
</script>

<style scoped>
.partner-card {
    background-color: #F7F8FA;
    padding: 16px;
    border-radius: 16px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.logo {
    max-width: 100%;
    height: auto;
}
</style>