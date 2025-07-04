<template>
    <section class="hero">
      <div class="container">
        <img :src="HeroBanner" alt="Hero image" class="heroImage" />

        <div class="contentCont">
            <h1 class="title">
                Создаём дизайн, который работает
            </h1>
            <p class="description">
                Идеи превращаем в результат — сайты, брендинг, презентации, от которых не оторваться.
            </p>
            <Button label="Обсудить проект" @click="handleClick" />
        </div>
        
      </div>
    </section>
</template>
  
<script setup lang="ts">
import Button from '../components/Button.vue'
import HeroBanner from '../assets/images/hero-banner.png'

const handleClick = () => {
alert('Кнопка нажата!')
}
</script>

<style scoped>
.hero {
width: 100%;
box-sizing: border-box;
padding: 42px 24px 32px;
}

.container {
margin: 0 auto;
}

.heroImage {
width: 100%;
aspect-ratio: 3/2;
object-fit: cover;
border-radius: 16px;
}

.contentCont {
max-width: 1280px;
margin: 0 auto;
}

.title {
font-size: 1.5rem;
margin: 0;
}

.description {
font-size: 1rem;
color: #4b5563;
margin: 0;
}

@media (min-width: 768px) {
.hero {
    padding: 0;
}

.heroImage {
    aspect-ratio: auto;
    border-radius: 0;
}

.title {
    font-size: 2.5rem;
}

.description {
    font-size: 1.25rem;
}
}
</style>