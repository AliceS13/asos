<template>
    <div class="content">
        <div class="content__container">
            <div class="content__image">
                <ImageJpgWrapper :imageName="imageId"/>
            </div>
            <div class="content__heading">
                <Heading title="This is ASOS" :level="1" heading="h1" heading-color="white" />
                <Heading title="ASOS DESIGN and 850+ brands" :level="2" heading="h2" heading-color="white"/>
                <div class="content__heading-buttons">
                    <Button color="white">Shop Women</Button>
                    <Button color="white">Shop Men</Button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import ImageJpgWrapper from '@/components/global/ImageJpgWrapper'
import Heading from '@/components/global/Heading'
import Button from '@/components/global/Button'

export default {
    name: 'Content',
    components: {
        ImageJpgWrapper, Heading, Button
    },
    data() {
        return {
            imageId: 'content-bg'
        }
    }
}
</script>

<style lang="scss">
    .content {
        max-height: 698px;
        &__container {
            max-width: 1400px;
            margin: 0 auto;
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        &__heading {
            z-index: 2;
            position: absolute;
            height: 200px;
            width: 360px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: space-between;
        }
        &__heading-buttons {
            width: 100%;
            display: flex;
            justify-content: space-between;
        }
    }
</style>