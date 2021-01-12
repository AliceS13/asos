<template>
    <div class="image-wrapper">
        <img :src="imageSrc" />
    </div>
</template>


<script>
export default {
    name: 'ImageJpgWrapper',
    props: {
        imageName: {
            type: String
        }
    },
    data() {
        return {
            imageSrc: require('@/assets/images/' + this.imageName + '.jpg')
        }
    }
}
</script>

<style lang="scss" scoped>
    .image-wrapper {
        img {
            width: 100%;
        }
    }
</style>
