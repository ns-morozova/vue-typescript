<template>
    <header class="header">
      <div class="container">
        <!-- Логотип -->
        <div class="logo">
          <a href="#" @click.prevent>
            <img src="../assets/logo.svg" alt="Logo" />
          </a>
        </div>
  
        <!-- Бургер-меню (только мобильное) -->
        <button class="mobile-menu-button" @click="toggleMobileMenu">
          <span v-if="!mobileMenuOpen">☰</span>
          <span v-else>✕</span>
        </button>
  
        <!-- Мобильное меню -->
        <transition name="slide">
          <div v-show="mobileMenuOpen" class="mobile-menu">
            <ul>
              <li v-for="(item, index) in navigation" :key="index">
                <a :href="item.href" @click="mobileMenuOpen = false">{{ item.name }}</a>
              </li>
              <li>
                <a href="#" @click="mobileMenuOpen = false">Связаться</a>
              </li>
            </ul>
          </div>
        </transition>
  
        <!-- Меню (десктоп) -->
        <nav class="desktop-menu">
          <ul>
            <li v-for="(item, index) in navigation" :key="index">
              <a :href="item.href">{{ item.name }}</a>
            </li>
          </ul>
        </nav>
  
        <!-- Кнопка "Связаться" (только десктоп) -->
        <!-- <div class="login-button desktop-login">
          <a href="#">Связаться</a>
        </div> -->
        <Button label="Связаться" class="desktop-login" />
      </div>
    </header>
</template>
  
<script setup>
import { ref } from 'vue'
import Button from '../components/Button.vue'

const navigation = [
    { name: 'О нас', href: '#about' },
    { name: 'Кейсы', href: '#cases' },
    { name: 'Услуги', href: '#services' },
    { name: 'Отзывы', href: '#reviews' },
    { name: 'Контакты', href: '#contacts' },
]

const mobileMenuOpen = ref(false)

function toggleMobileMenu() {
mobileMenuOpen.value = !mobileMenuOpen.value
}
</script>

<style scoped>
/* Base styles for mobile */
.header {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 1000;
    background-color: #fff;
    border-bottom: 1px solid #e5e7eb;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
}

.container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    max-width: 1280px;
    margin: 0 auto;
    padding: 16px 24px;
    box-sizing: border-box;
}

.logo {
    height: 32px;
}

.logo img {
    height: 100%;
}

.mobile-menu-button {
    display: block;
    background: none;
    border: none;
    font-size: 24px;
    cursor: pointer;
    padding: 0;
}

.mobile-menu {
    position: absolute;
    top: 100%;
    left: 0;
    right: 0;
    background-color: white;
    padding: 16px 24px;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
    z-index: 10;
}

.mobile-menu ul {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 12px;
}

.mobile-menu ul li a {
    text-decoration: none;
    color: #1f2937;
    font-size: 16px;
    font-weight: 500;
}

.slide-enter-active,
.slide-leave-active {
    transition: all 0.3s ease;
}
.slide-enter-from,
.slide-leave-to {
    transform: translateY(-10px);
    opacity: 0;
}

.desktop-menu,
.desktop-login {
    display: none;
}

/* Desktop styles */
@media (min-width: 992px) {
    .container {
        padding: 16px;
    }

    .mobile-menu-button {
        display: none;
    }

    .mobile-menu {
        display: none;
    }

    .desktop-menu {
        flex-grow: 1;
        display: flex;
        justify-content: center;
    }

    .desktop-menu ul {
        list-style: none;
        display: flex;
        gap: 40px;
        padding: 0;
    }

    .desktop-menu ul li a {
        text-decoration: none;
        color: #1f2937;
        font-size: 14px;
        line-height: 20px;
        font-weight: 400;
    }

    .desktop-login {
        display: block;
    }
}
</style>