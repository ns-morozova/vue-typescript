<template>
    <div class="benefitCard">
      <div class="iconWrapper">
        <img :src="icon" :alt="title" class="icon" />
      </div>
      <h3 class="cardTitle">{{ title }}:</h3>
      <p class="description">{{ text }}</p>
    </div>
</template>
  
<script setup lang="ts">
defineProps<{
    icon: string;
    title: string;
    text: string;
}>();
</script>

<style scoped>
.benefitCard {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    padding: 24px;
    color: #fff;
}

.iconWrapper {
    width: 64px;
    height: 64px;
    border-radius: 24px;
    /* background: linear-gradient(135deg, #44ff9a, #44b0ff); */
    background: linear-gradient(135deg, #ff7c5e, #8B44FF);
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
    margin-bottom: 24px;
}

.icon {
    width: 32px;
    height: 32px;
    object-fit: contain;
}

.cardTitle {
    font-size: 18px;
    line-height: 28px;
    font-weight: 600;
    margin-bottom: 8px;
}

.description {
    font-size: 16px;
    line-height: 24px;
    width: 95%;
}

@media (min-width: 992px) {
    .description {
        width: 70%;
    }
}

@media (min-width: 1280px) {
    .description {
        width: 55%;
    }
}
</style>