<template>
    <section class="benefits">

      <div class="container">
        <h2 class="title">
            Почему мы
        </h2>

        <div class="benefitsList">
            <BenefitCard
            v-for="(card, index) in cards"
            :key="index"
            :icon="card.icon"
            :title="card.title"
            :text="card.text"
            />
        </div>
      </div>

      <div class="gradient"></div>

    </section>
</template>
  
<script setup lang="ts">
import BenefitCard from '../components/BenefitCard.vue';

import Benefit1 from '../assets/images/icons/benefit1.svg';
import Benefit2 from '../assets/images/icons/benefit2.svg';
import Benefit3 from '../assets/images/icons/benefit3.svg';
import Benefit4 from '../assets/images/icons/benefit4.svg';

const cards = [
  {
    icon: Benefit1,
    title: 'Погружаемся в ваш бизнес',
    text: 'интервью, анализ, исследование, чтобы понять задачу глубже',
  },
  {
    icon: Benefit2,
    title: 'Делаем быстро',
    text: 'от идеи до релиза — без воды и промедлений',
  },
  {
    icon: Benefit3,
    title: 'Сопровождаем проект до конца и после',
    text: 'мы не просто создаём дизайн, мы строим партнёрские отношения',
  },
  {
    icon: Benefit4,
    title: 'Любим проекты',
    text: 'относимся к ним как к своим, с полной отдачей',
  },
];
</script>

<style scoped>
.benefits {
    position: relative;
    width: 100%;
    box-sizing: border-box;
    padding: 64px 24px 48px;
    background-color: #000;
    color: #fff;
    border-radius: 32px;
    overflow: hidden;
}

.gradient {
    position: absolute;
    width: 60%;
    height: 120%;
    top: 50%;
    right: 85%;
    transform: translateY(-50%);
    background-image: radial-gradient(
    circle,
    #44FF9A,
    #44B0FF,
    #8B44FF,
    #FF6644,
    #EBFF70
  );
  filter: blur(100px);
}

.container {
    position: relative;
    max-width: 1280px;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    z-index: 2;
}

.title {
    font-size: 30px;
    line-height: 38px;
    font-weight: 700;
    margin-bottom: 56px;
}

.benefitsList {
    display: grid;
    gap: 16px;
}

@media (min-width: 768px) {
    .benefits {
        padding: 140px 0 100px;
    }

    .gradient {
        width: 30%;
        height: 120%;
        right: 95%;
    }

    .title {
        font-size: 64px;
        line-height: 64px;
        margin-bottom: 88px;
    }

    .benefitsList {
        grid-template-columns: repeat(2, 1fr);
    }
}
</style>