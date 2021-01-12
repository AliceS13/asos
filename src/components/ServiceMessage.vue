<template>
    <div class="service-message">
        <div class="service-message__container">
            <div class="service-message__item">
                <div class="service-message__item-icon">
                    <ImageSvgWrapper :imageName="imagesId[0]"/>
                </div>
                <div class="service-message__item-text">
                    <Heading class="service-message__item-title" title="EASY DELIVERY WORLDWIDE" :level="3" heading="h3" heading-color="white"/>
                    <Heading class="service-message__item-title" title="MORE INFO HERE" :level="4" heading="h4" heading-color="white"/>
                </div>
            </div>
            <div class="service-message__item">
                <div class="service-message__item-icon">
                    <ImageSvgWrapper :imageName="imagesId[1]"/>
                </div>
                <div class="service-message__item-text">
                    <Heading class="service-message__item-title" title="DISCOVER OVER 850 BRANDS" :level="3" heading="h3" heading-color="white"/>
                    <Heading class="service-message__item-title" title="+ NEW DROPS WEEKLY" :level="4" heading="h4" heading-color="white"/>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import ImageSvgWrapper from '@/components/global/ImageSvgWrapper'
import Heading from '@/components/global/Heading'
export default {
    name: 'ServiceMessage',
    components: {
        ImageSvgWrapper, Heading
    },
    data() {
        return {
            imagesId: ['delivery-icon', 'tag-icon']
        }
    }   
}
</script>


<style lang="scss"> 
    .service-message {
        margin: -4px 0 0 0;
		&__container {
            max-width: 1400px;
            display: flex;
            justify-content: space-between;
            background: #2d2d2d;
            margin: 0 auto;
            padding: 10px 0;
		}
		&__item {
            display: flex;
            flex: 1 1 50%;
            align-items: center;
            justify-content: center;

		}
		&__item-icon {
            margin: 0 10px 0 0;
        }
    }
</style>