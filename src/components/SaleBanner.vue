<template>
  <div class="sale-banner">
    <div class="container sale-banner__container">
      <Button :title="buttonTitle">Women</Button>
      <div class="sale-banner__text">
        <div class="sale-banner__text-item" v-for="(promotion, index) of promotions" :key="index">
          {{ promotion }}
        </div>
      </div>
      <Button :title="buttonTitle">Men</Button>

    </div>
  </div>
</template>

<script>
import Button from '@/components/global/Button'
import siteConfig from '../../siteConfig'

export default {
  name: 'SaleBanner',
  components: {
    Button
  },
  props: {
    promotions: {
      type: Array
    },
  },
  data() {
    return {
      buttonTitle: siteConfig.header.title
    }
  }
}
</script>

<style scoped lang="scss">

.sale-banner {
    background: rgb(154, 214, 174);
  &__container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 9px 32px;
  }
  &__text {
    display: flex;
    flex-direction: column;
    align-items: center;
    font-weight: 700;
    letter-spacing: 2px;
  }
}
  
</style>
