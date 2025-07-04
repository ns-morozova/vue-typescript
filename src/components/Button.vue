<template>
    <button class="button" @click="$emit('click')">
      {{ label }}
    </button>
</template>
  
<script setup lang="ts">
defineProps<{
  label: string
}>()

defineEmits<{
  (e: 'click'): void
}>()
</script>

<style scoped>
.button {
  box-sizing: border-box;
  padding: 0.75rem 1.5rem;
  background-color: #000;
  color: white;
  border: 1px #000 solid;
  outline: none;
  border-radius: 0.375rem;
  font-weight: 700;
  cursor: pointer;
  transition: all 0.3s ease;
}

.button:hover {
  background-color: #fff;
  color: #000;
}
</style>