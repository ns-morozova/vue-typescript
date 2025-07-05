<template>
    <button class="button" @click="$emit('click')">
      <div class="buttonContent">
        {{ label }}
      </div>
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
  position: relative;
  box-sizing: border-box;
  padding: 0;
  outline: none;
  border: none;
  cursor: pointer;
  z-index: 2;
}

.buttonContent {
  position: relative;
  box-sizing: border-box;
  padding: 16px;
  border-radius: 8px;
  background-color: #000;
  color: white;
  font-size: 16px;
  line-height: 24px;
  font-weight: 700;
  z-index: 2;
}

.button::before {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 110%;
  height: 90%;
  background-image: radial-gradient(
    circle,
    #44FF9A,
    #44B0FF,
    #8B44FF,
    #FF6644,
    #EBFF70
  );
  filter: blur(10px);
  opacity: 0;
  z-index: 1;
  transition: opacity 0.3s ease;
}

.button:hover::before {
  opacity: 1;
}

@media (min-width: 992px) {
    .buttonContent {
      padding: 12px 20px;
      font-size: 14px;
      line-height: 20px;
    }
}
</style>