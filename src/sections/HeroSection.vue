<template>
    <section class="hero">
      <div class="container">
        <img :src="HeroBanner" alt="Hero image" class="heroImage" />

        <div class="contentCont">
            <div class="content">
                <h1 class="title">
                Создаём дизайн, который работает
                </h1>
                <div>
                    <p class="description">
                        Идеи превращаем в результат — сайты, брендинг, презентации, от которых не оторваться.
                    </p>
                    <button type="button" @click="handleClick" class="btnHero">
                        <div class="btnHeroContent">
                            Обсудить проект
                        </div>
                    </button>
                </div>
            </div>
            
            
        </div>
        
      </div>
    </section>
</template>
  
<script setup lang="ts">
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
    position: relative;
    width: 100%;
    /* max-width: 1280px; */
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    gap: 32px;
}

.heroImage {
    width: 100%;
    aspect-ratio: 3/2;
    object-fit: cover;
    border-radius: 16px;
}

/* .contentCont {
    display: flex;
    flex-direction: column;
    gap: 16px;
} */

.content {
    display: flex;
    flex-direction: column;
    gap: 16px;
}

.title {
    font-size: 24px;
    font-weight: 600;
    text-transform: uppercase;
}

.description {
    font-size: 16px;
    line-height: 24px;
}

/* .btnHero {
    background-color: #000;
    color: #fff;
    font-size: 16px;
    line-height: 24px;
    font-weight: 700;
    padding: 16px;
    border: none;
    outline: none;
} */

.content div {
    display: flex;
    flex-direction: column;
    gap: 16px;  
}

.btnHero {
  position: relative;
  padding: 0;
  outline: none;
  border: none;
  cursor: pointer;
  z-index: 2;
}

.btnHeroContent {
  position: relative;
  padding: 16px;
  border-radius: 8px;
  background-color: #000;
  color: #fff;
  font-size: 16px;
  line-height: 24px;
  font-weight: 700;
  z-index: 2;
}

.btnHero::before {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 100%;
  height: 100%;
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

.btnHero:hover::before {
  opacity: 1;
}

@media (min-width: 640px) {
    .title, .description {
        width: 70%;
    }
}

@media (min-width: 768px) {
    .hero {
        padding: 0;
    }

    .heroImage {
        aspect-ratio: auto;
        border-radius: 0;
    }

    .contentCont {
        position: absolute;
        top: 90%;
        width: 100%;
        padding: 0 24px 24px;
        box-sizing: border-box;
        border-bottom-left-radius: 32px;
        border-bottom-right-radius: 32px;
        background-color: #010101;
        color: #fff;
    }

    .content {
        width: 100%;
        max-width: 1280px;
        margin: 0 auto;
        flex-direction: row;
        align-items: center;
    }

    .title, .description {
        width: 100%;
    }

    .title {
        font-size: 36px;
        line-height: 52px;
        min-width: 50%;
    }

    .description {
        font-size: 18px;
        line-height: 22px;
    }

    .content div {
        justify-content: space-between;

    }

    .btnHeroContent {
        background-color: #fff;
        color: #000;
        padding: 12px 20px;
    }
}

@media (min-width: 992px) {
    .content {
        gap: 88px;
    }

    .title {
        font-size: 48px;
        line-height: 1.2;
    }
}

@media (min-width: 1280px) {
    .title {
        font-size: 56px;
    }

    .description {
        font-size: 18px;
        line-height: 28px;
    }
}

@media (min-width: 1440px) {
    .contentCont {
        padding: 0 80px 68px;
    }

    .title {
        font-size: 68px;
    }
}
</style>