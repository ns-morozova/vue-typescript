<template>
    <header class="header">
      <div class="container">
        <!-- Logo -->
        <div class="logo">
          <a href="#" @click.prevent="scrollToTop">
            <img src="../assets/logo.svg" alt="Logo" />
          </a>
        </div>

        <!-- Mobile menu -->
        <transition name="fade">
            <div v-show="mobileMenuOpen" >
                <div class="menuMobile">
                  <ul>
                      <li v-for="(item, index) in navigation" :key="index">
                      <a :href="item.href" @click="mobileMenuOpen = false">{{ item.name }}</a>
                      </li>
                  </ul>
                  <div class="contactsMobile">
                    <div class="iconsMobile">
                      <ContactIcon v-for="(icon, index) in contactIcons" :key="index" :icon-src="icon.src" />
                    </div>
                    <Button label="Связаться" @click="mobileMenuOpen = false" class="btnMobile" />
                  </div>
                  
                </div>
            </div>
        </transition>

        <!-- Burger (mob) -->
        <button class="burgerMobile" @click="toggleMobileMenu">
          {{ mobileMenuOpen ? '✕' : '☰' }}
        </button>
  
        <!-- Menu (desktop) -->
        <nav class="menuDesktop">
          <ul>
            <li v-for="(item, index) in navigation" :key="index">
              <a :href="item.href">{{ item.name }}</a>
            </li>
          </ul>
        </nav>
  
        <!-- Contacts (desktop) -->
         <div class="contactsDesktop">
          <div class="iconsDesktop">
            <ContactIcon v-for="(icon, index) in contactIcons" :key="index" :icon-src="icon.src" />
          </div>
          <Button label="Связаться" />
         </div>
      </div>
    </header>
</template>
  
<script setup lang="ts">
import { ref } from 'vue'
import Button from '../components/Button.vue'
import ContactIcon from './ContactIcon.vue'
import Telegram from '../assets/images/icons/telegram.svg';
import Whatsapp from '../assets/images/icons/whatsapp.svg';

const navigation = [
    { name: 'О нас', href: '#about' },
    { name: 'Кейсы', href: '#cases' },
    { name: 'Услуги', href: '#services' },
    { name: 'Отзывы', href: '#reviews' },
    { name: 'Контакты', href: '#contacts' },
]

const contactIcons = [
  { src: Telegram },
  { src: Whatsapp },
]

const mobileMenuOpen = ref(false)

function scrollToTop() {
  window.scrollTo({
    top: 0,
    behavior: 'smooth'
  })
}

function toggleMobileMenu() {
  mobileMenuOpen.value = !mobileMenuOpen.value

  const body = document.body

  if (mobileMenuOpen.value) {
    body.style.overflow = 'hidden'
  } else {
    body.style.overflow = ''
  }
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
  box-shadow: 0 2px 12px rgba(0, 0, 0, 0.15);
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

.burgerMobile {
  display: block;
  background: none;
  border: none;
  outline: none;
  font-size: 24px;
  cursor: pointer;
  padding: 0;
}

.overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: rgba(0, 0, 0, 0);
  z-index: 20;
  display: flex;
  align-items: center;
  justify-content: center;
}

.menuMobile {
  position: fixed;
  inset: 0;
  top: 76px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 16px 24px;
  background-color: white;
}

.menuMobile ul {
  list-style: none;
  display: flex;
  flex-direction: column;
  padding: 0;
  margin: 0;
}

.menuMobile ul li {
  padding: 12px 0;
  border-bottom: 1px #DDDDDD solid;
}

.menuMobile ul li:last-child {
  border-bottom: none;
}

.menuMobile ul li a {
  text-decoration: none;
  color: #141414;
  font-size: 18px;
  line-height: 28px;
  font-weight: 400;
}

.contactsMobile {
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.iconsMobile {
  display: flex;
  gap: 8px;
}

.btnMobile {
  width: 100%;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.menuDesktop, .contactsDesktop {
    display: none;
}

@media (min-width: 768px) {
  .menuMobile {
    top: 72px;
  }
}

/* Desktop styles */
@media (min-width: 992px) {
  .header {
    top: 20px;
    background: none;
    box-shadow: none;
  }

  .container {
    padding: 16px;
    background-color: #fff;
    border-radius: 24px;
    box-shadow: 0 2px 12px rgba(0, 0, 0, 0.20);
  }

  .burgerMobile {
    display: none;
  }

  .menuMobile {
    display: none;
  }

  .menuDesktop {
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    flex-grow: 1;
    display: flex;
    justify-content: center;
  }

  .menuDesktop ul {
    list-style: none;
    display: flex;
    gap: 40px;
    padding: 0;
    margin: 0;
  }

  .menuDesktop ul li a {
    text-decoration: none;
    color: #1f2937;
    font-size: 14px;
    line-height: 20px;
    font-weight: 400;
  }

  .contactsDesktop {
    display: flex;
    align-items: center;
    gap: 24px;
  }

  .iconsDesktop {
    display: flex;
    gap: 12px;
  }
}
</style>