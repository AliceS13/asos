<template>
  <div class="home">
    <Header />
    <SaleBanner :promotions="homePagePromotions" />
    <Content />
    <ServiceMessage />
    <Footer :icons="['facebook-icon', 'instagram-icon', 'snapchat-icon']" :images="['visa', 'mastercard', 'pay-pal', 'american-express', 'visa-electron']" buttonImage="ua" />
  </div>
</template>

<script>
// @ is an alias to /src
import Header from '@/components/Header'
import SaleBanner from '@/components/SaleBanner'
import Content from '@/components/Content'
import ServiceMessage from '@/components/ServiceMessage'
import Footer from '@/components/Footer'
import siteConfig from '../../siteConfig'


export default {
  name: 'Home',
  components: {
    Header, SaleBanner, Content, ServiceMessage, Footer
  },
  data() {
    return {
      homePagePromotions: siteConfig.pages.home.promotions
    }
  }
}
</script>

<style lang="scss">
    
</style>
