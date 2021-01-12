<template>
    <div class="header">
        <div class="container header__container">
            <Logo />
            <CategoryNavigation :items="categories"/>
            <Search />
            <HeaderNavigation />
        </div>
    </div>
</template>

<script>
import Logo from '@/components/Logo'
import CategoryNavigation from "@/components/CategoryNavigation"
import siteConfig from '../../siteConfig'
import Search from '@/components/Search'
import HeaderNavigation from '@/components/HeaderNavigation'


export default {
    name: 'Header',
    components: {
        Logo, CategoryNavigation, Search, HeaderNavigation
    },
    data() {
        return {
            categories: siteConfig.header.categories,
            svgIcons: siteConfig.svgImages
        }
    }
}
</script>

<style lang="scss">
    .header {
        position: relative;
        z-index: 200;
        height: 60px;
        background: #2d2d2d;
        &__container {
            padding: 0 32px;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }
    }

    .container {
        max-width: 1366px;
        margin: 0 auto;
    }

    
</style>