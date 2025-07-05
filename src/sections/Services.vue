<template>
    <section class="services">
      <div class="container">
        <h2 class="title">
            Что мы делаем
        </h2>
        <p class="description">
            Создаём продукты и визуальные системы под ключ. Берём на себя всё: от позиционирования и айдентики до UX/UI-дизайна, разработки и внедрения.
        </p>
      </div>
    </section>
</template>
  
<script setup lang="ts">

</script>

<style scoped>
.services {
    width: 100%;
    box-sizing: border-box;
    padding: 32px 24px 32px;
}

.container {
    max-width: 1280px;
    margin: 0 auto;
}

.title {
    font-size: 30px;
    line-height: 38px;
    font-weight: 700;
    margin-bottom: 16px;
}

.description {
    font-size: 16px;
    line-height: 24px;
}

@media (min-width: 768px) {
    .services {
        padding: 50px 24px;
    }

    .title {
        font-size: 64px;
        line-height: 64px;
        margin-bottom: 36px;
    }

    .description {
        width: 92%;
    }
}

@media (min-width: 992px) {
    .description {
        width: 75%;
    }
}

@media (min-width: 1280px) {
    .description {
        width: 62%;
    }
}
</style>