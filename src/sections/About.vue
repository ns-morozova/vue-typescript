<template>
    <section class="about">
      <div class="container">
        <div class="textBlock">
            <h2 class="title">
                Кто мы?
            </h2>
            <p class="description">
                Мы — креативная команда дизайнеров, разработчиков и стратегов. Вместе мы создаём сайты и брендинг, которые приносят результат, 
                а не просто выглядят красиво. Работаем с бизнесом, стартапами 
                и IT-компаниями, которым нужен понятный и выразительный визуальный стиль.
            </p>
        </div>

        <p class="approach">
            Наш подход — минимализм с глубиной, где каждый пиксель решает задачу, а не просто украшает
        </p>

        <div class="cards">
            <StatCard v-for="(card, index) in cards" :key="index" :number="card.number" :description="card.description" />
      </div>
      </div>
    </section>
</template>
  
<script setup lang="ts">
import StatCard from '../components/StatCard.vue';

const cards = [
  { number: '12', description: 'лет опыта на рынке' },
  { number: '200', description: 'выполненных проектов' },
  { number: '20', description: 'проектов с IT-компаниями и стартапами' },
]
</script>

<style scoped>
.about {
    width: 100%;
    box-sizing: border-box;
    padding: 32px 24px 32px;
}

.container {
    max-width: 1280px;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    gap: 48px;
}

.textBlock {
    display: flex;
    flex-direction: column;
    gap: 16px;
}

.title {
    font-size: 30px;
    line-height: 38px;
    font-weight: 700;
}

.description {
    font-size: 16px;
    line-height: 24px;
    margin: 0;
}

.approach {
    font-size: 28px;
    line-height: 100%;
    font-weight: 600;
}

.cards {
    display: flex;
    flex-direction: column;
    gap: 16px;
}

@media (min-width: 768px) {
    .about {
        padding: 100px 0;
    }

    .container {
        gap: 56px;
    }

    .textBlock {
        flex-direction: row;
        justify-content: space-between;
        align-items: flex-start;
    }

    .title {
        font-size: 64px;
        line-height: 64px;
    }

    .description {
        width: 50%;
    }

    .approach {
        font-size: 32px;
    }

    .cards {
        flex-direction: row;
        gap: 24px;
    }
}

@media (min-width: 1120px) {
    .approach {
        font-size: 32px;
        max-width: 92%;
    }
}
</style>