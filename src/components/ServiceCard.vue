<template>
    <div class="serviceCard">
        <h3 class="cardTitle">{{ title }}</h3>
        <p class="cardDescription">{{ description }}</p>
        <Button label="Заказать" class="orderButton" />

        <button class="toggleBtn" @click="toggle">
            <img v-if="!isOpen" :src="arrowDown" alt="Узнать больше" class="icon" />
            <img v-else :src="arrowUp" alt="Скрыть" class="icon" />
            {{ isOpen ? 'Скрыть подробности' : 'Узнать больше' }}
        </button>
  
        <transition name="slide">
            <ul v-show="isOpen" class="pointsList">
                <li v-for="(point, index) in points" :key="index" class="pointItem">
                    <img :src="arrowPoint" alt="Подробности" class="icon" />
                    {{ point }}
                </li>
            </ul>
        </transition>
    </div>
</template>
  
<script setup lang="ts">
import { ref, watchEffect } from 'vue'

import Button from './Button.vue';

import arrowDown from '../assets/images/icons/arrowDown.svg';
import arrowUp from '../assets/images/icons/arrowUp.svg';
import arrowPoint from '../assets/images/icons/arrowPoint.svg';

const props = defineProps<{
  title: string
  description: string
  points: string[]
  isInitiallyOpen?: boolean
}>()

const isOpen = ref(props.isInitiallyOpen || false)

watchEffect(() => {
  isOpen.value = props.isInitiallyOpen || false
})

const toggle = () => {
    isOpen.value = !isOpen.value
}
</script>

<style scoped>
.serviceCard {
    position: relative;
    background-color: #fff;
    border: 2px #F2F2F2 solid;
    border-radius: 12px;
    padding: 32px 24px;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
    color: #050505;
}

.cardTitle {
    font-size: 16px;
    line-height: 24px;
    font-weight: 700;
    margin-bottom: 24px;
}

.cardDescription {
    font-size: 14px;
    line-height: 20px;
    margin-bottom: 24px;
}

.orderButton {
    width: 100%;
    margin-bottom: 24px;
}

.toggleBtn {
    background: none;
    border: none;
    outline: none;
    padding: 0;
    display: flex;
    align-items: center;
    gap: 12px;
    color: #050505;
    font-size: 14px;
    line-height: 20px;
    font-weight: 700;
    text-decoration: underline;
    text-underline-offset: 4px;
    cursor: pointer;
}

.pointsList {
    list-style: none;
    padding-left: 0;
    margin: 24px 0 0 0;
}

.pointItem {
    display: flex;
    align-items: center;
    gap: 16px;
    font-size: 14px;
    line-height: 20px;
    color: #000;
    margin-bottom: 8px;
}

/* Анимация открытия/закрытия */
.slide-enter-active,
.slide-leave-active {
    transition: max-height 0.3s ease-out;
    max-height: 400px;
}
.slide-enter-from,
.slide-leave-to {
    max-height: 0;
}

@media (min-width: 768px) {
    .cardTitle {
        font-size: 22px;
        line-height: 28px;
        margin-bottom: 24px;
    }

    .cardDescription {
        font-size: 16px;
        line-height: 24px;
    }

    .pointItem {
        font-size: 16px;
        line-height: 24px;
    }

    .orderButton {
        width: 135px;
    }
}

@media (min-width: 992px) {
    .cardDescription {
        width: 85%;
    }

    .orderButton {
        width: max-content;
        position: absolute;
        top: 32px;
        right: 24px;
    }
}
</style>