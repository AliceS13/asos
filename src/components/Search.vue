<template>
    <div class="search">
        <input class="search__input" type="search" name="" id="" :placeholder="placeholderMessage">
        <div class="search__icon">
            <ImageSvgWrapper :title="titleText" :imageName="searchIcon"/>
        </div>
    </div>
</template>

<script>
import ImageSvgWrapper from '@/components/global/ImageSvgWrapper'
import Button from './global/Button.vue'
export default {
    name: 'Search',
    components: { ImageSvgWrapper },
    data() {
        return {
            placeholderMessage: 'Search for items, brands and inspiration',
            searchIcon: 'search-icon',
            titleText: 'Search'
        }
    }
}
</script>

<style lang="scss">
    
    .search {
        flex: 1 1 auto;
        padding: 11px 15px 11px 30px;
        position: relative;
        &__input {
            width: 100%;
            height: 38px;
            border-radius: 19px / 50%;
            padding: 1px 70px 1px 16px;
        }
        &__icon {
            width: 16px;
            height: 16px;
            position: absolute;
            right: 25px;
            top: calc(50% - 8px);
            cursor: pointer;
        }
    }

</style>