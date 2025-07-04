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
    padding: 0.75rem 1.5rem;
    background-color: #3b82f6;
    color: white;
    border: none;
    border-radius: 0.375rem;
    cursor: pointer;
    font-weight: bold;
    transition: background-color 0.3s ease;
  }
  
  .button:hover {
    background-color: #2563eb;
  }
  </style>