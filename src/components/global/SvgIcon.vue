<template>
    <div>
        <span v-html="iconSrc"></span>
    </div>
</template>

<script>
import siteConfig from '../../../siteConfig'

export default {
    props: {
        id: {
            type: String,
            required: true
        }
    },
    data() {
        const iconSrc = siteConfig.svgImages[this.id]
        return {
            iconSrc
        }
    }
}
</script>