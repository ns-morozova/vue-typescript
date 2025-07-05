<template>
    <section class="partners">
      <div class="container">
        <h2 class="title">
            Нам доверяют
        </h2>

        <div class="partnersList">
            <PartnerCard v-for="(partner, index) in partners" :key="index" :logo="partner.logo" />
        </div>
      </div>
    </section>
</template>
  
<script setup lang="ts">
import PartnerCard from '../components/PartnerCard.vue';

import Anzu from '../assets/images/partners/anzu.svg';
import Aicraft from '../assets/images/partners/aicraft.svg';
import Len from '../assets/images/partners/len.svg';
import Viterm from '../assets/images/partners/viterm.svg';
import Mash from '../assets/images/partners/mash.svg';
import Corn from '../assets/images/partners/corn.svg';

const partners = [
  { logo: Anzu },
  { logo: Aicraft },
  { logo: Len },
  { logo: Viterm },
  { logo: Mash },
  { logo: Corn },
]
</script>

<style scoped>
.partners {
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
    margin-bottom: 48px;
}

.partnersList {
    display: grid;
    gap: 16px;
}

@media (min-width: 768px) {
    .partners {
        padding: 50px 0;
    }

    .title {
        font-size: 64px;
        line-height: 64px;
        margin-bottom: 64px;
    }

    .partnersList {
        /* grid-template-columns: repeat(auto-fit, minmax(150px, 1fr)); */
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (min-width: 992px) {
    .partnersList {
        grid-template-columns: repeat(3, 1fr);
    }
}
</style>