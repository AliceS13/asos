<template>
    <div class="nav">
        <div class="nav__item" v-for="item of items" :key="item.id">
            <router-link class="nav__item-link" :to="'category/' + item.id">
                {{ item.displayName }}
            </router-link>
        </div>
    </div>
</template>

<script>


export default {
    name: 'CategoryNavigation',
    props: {
        items: {
            type: Array
        }
    }
}
</script>

<style lang="scss">
.nav {
    display: flex;
    &__item {
        width: 100px;
        display: flex;
        align-items: center;
        justify-content: center;
        &:first-child {
            border-left: 1px solid #525050;
            border-right: 1px solid #525050;
        }
        &:last-child {
            border-right: 1px solid #525050;
        }
        &:hover {
            background: #525050;
        }
    }
    &__item-link {
        display: block;
        line-height: 60px;
        color: #fff;
        text-decoration: none;
        text-transform: uppercase;
        margin: 0 18px;
        height: 100%;
        letter-spacing: 2px;
    }
}

</style>