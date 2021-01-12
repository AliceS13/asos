<template>
    <div>
        <h1>{{ categoryId }} page</h1>
        <pre>
            {{ products }}
        </pre>
    </div>
</template>

<script>
import siteConfig from '../../siteConfig'

export default {
    data() {
        const categoryId = this.$route.params.id

        const products = siteConfig.products.filter(product => product.categories.includes(categoryId))
        return {
            categoryId,
            products
        }
    }
}
</script>