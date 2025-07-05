<template>
    <div class="statCard">
        <div class="cardContent">
            <span class="number">{{ number }}+</span>
            <p class="description">{{ description }}</p>
        </div>
        <div class="blur"></div>
    </div>
</template>
  
<script setup lang="ts">
defineProps<{
    number: string | number
    description: string
}>()
</script>

<style scoped>
.statCard {
    position: relative;
    width: 100%;
    background-color: #050505;
    color: #fff;
    border-radius: 16px;
    padding: 20px 20px 24px;
    box-sizing: border-box;
    overflow: hidden;
}

.cardContent {
    position: relative;
    z-index: 2;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 8px;
    text-align: center;
}

.number {
    font-size: 64px;
    line-height: 64px;
    font-weight: 700;
}

.description {
    font-size: 16px;
    line-height: 24px;
}

.blur {
    position: absolute;
    top: 100%;
    left: 50%;
    transform: translateX(-50%);
    width: 100%;
    height: 100%;
    background-color: #fff;
    opacity: 80%;
    filter: blur(80px);
    z-index: 1;
}
</style>