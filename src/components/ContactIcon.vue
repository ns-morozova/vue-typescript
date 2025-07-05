<template>
    <div class="contactIcon">
      <img :src="iconSrc" alt="Contact Icon" class="icon" />
    </div>
</template>
  
<script setup lang="ts">

defineProps<{
    iconSrc: string
}>()
</script>

<style scoped>
.contactIcon {
    width: 32px;
    height: 32px;
    flex-shrink: 0;
    border-radius: 50%;
    overflow: hidden;
    cursor: pointer;
}

.icon {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

@media (min-width: 992px) {
    .contactIcon {
        width: 24px;
        height: 24px;
    }
}
</style>