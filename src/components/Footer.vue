<template>
    <div class="footer">
        <div class="footer__links">
            <div class="footer__links-social social-links" >
                <a class="social-links__link" v-for="icon of icons" :key="icon">
                    <SvgIcon :id="icon"/>
                </a>
            </div>
            <div class="footer__links-payment payment-links" >
                <a class="payment-links__link" v-for="image of images" :key="image">
                    <ImageJpgWrapper :imageName="image"/>
                </a>
            </div>
        </div>
        <div class="footer__nav">
            <div class="container">
                <div class="footer__nav-items">
                    <div class="footer__nav-item nav-item" v-for="(navigationItem, index) in navigationTaxonomy" :key="index">
                        <div class="nav-item__title">
                            {{ navigationItem.title }}
                        </div>
                        <a v-for="(navigationLink, linkIndex) in navigationItem.items" :key="linkIndex" class="nav-item__link" :href="navigationLink.link">{{ navigationLink.title }}</a>
                    </div>
                    <div class="footer__nav-item nav-item">
                        <div class="nav-item__title">
                            SHOPPING FROM:
                        </div>
                        <div class="nav-item__body">
                            <span class="nav-item__text">You're in</span> 
                            <div class="nav-item__image-wrapper">
                                <div class="nav-item__image">
                                    <ImageJpgWrapper :imageName="buttonImage"/>
                                </div>
                            </div>
                            <button class="nav-item__button">Change</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="footer__bottom">
            <div class="footer__bottom-container container">
                <div class="footer__bottom-text">
                    <span>© 2020 ASOS</span>
                </div>
                <div class="footer__bottom-links">
                    <a :href="bottomLinks.link" class="footer__bottom-link" v-for="(bottomLink, bottomLinkIndex) in bottomLinks" :key="bottomLinkIndex">
                        {{ bottomLink.title }}
                    </a>
                </div>
            </div>
        </div>
    </div> 
</template>

<script>
import SvgIcon from '@/components/global/SvgIcon'
import ImageJpgWrapper from '@/components/global/ImageJpgWrapper'
import Heading from '@/components/global/Heading'

export default {
    name: 'Footer',
    components: {
        SvgIcon, ImageJpgWrapper, Heading
    },
    props: {
        icons: {
            type: Array
        }, 
        images: {
            type: Array
        },
        buttonImage: {
            type: String
        }
    },
    data() {
        return {
            navigationTaxonomy: [
                {
                    title: 'HELP & INFORMATION',
                    items: [
                        { link: '#', title: 'Help' },
                        { link: '#', title: 'Track Order' },
                        { link: '#', title: 'Delivery & Returns' }
                    ]
                },
                {
                    title: 'ABOUT ASOS',
                    items: [
                        { link: '#', title: 'About Us' },
                        { link: '#', title: 'Careers at ASOS' },
                        { link: '#', title: 'Corporate Responsibility' },
                        { link: '#', title: 'Investors Site' }
                    ]
                },
                {
                    title: 'MORE FROM ASOS',
                    items: [
                        { link: '#', title: 'Mobile and ASOS Apps' },
                        { link: '#', title: 'ASOS Marketplace' },
                        { link: '#', title: 'Gift vouchers' },
                        { link: '#', title: 'Black Friday' }
                    ]
                }
            ],
            bottomLinks: [
                { link: '#', title: 'Privacy & Cookies' },
                { link: '#', title: 'Ts&Cs' },
                { link: '#', title: 'Accessibility' }
            ]
        }
    }
}
</script>


<style lang="scss" scoped>
    .container {
        max-width: 1366px;
        margin: 0 auto;
    }
    .footer {
		&__links {
            display: flex;
            align-items: center;
            justify-content: center;
            border-top: 1px solid #eee;
		}
        &__nav {
            background: #eee;
		}
		&__nav-items {
            display: flex;
            justify-content: space-between;
            padding: 32px;
		}
        &__bottom {
            background: #ddd;
            font-weight: 400;
        }
		&__bottom-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 32px;
            
		}
        &__bottom-text {
            color: #2d2d2d;
            font-size: 12px;
        }
        &__bottom-link {
            color: #2d2d2d;
            font-size: 14px;
            position: relative;
            cursor: pointer;
            &:not(:last-child) {
                padding: 0 14px 0 0;
                &::after {
                    content: '|';
                    position: absolute;
                    right: 6px;
                }
            }
        }
    }
    .social-links {
        display: flex;
        padding: 0 50px 0 0;
        &__link {
            padding: 15px 0;
            &:hover {
                cursor: pointer;
            }
            &:not(:first-child) {
                margin: 0 0 0 50px;
            }
        }
    }
    .payment-links {
        display: flex;
        margin: 20px 0;
        padding: 0 0 0 50px;
        border-left: 1px solid #999;
        &__link {
            &:not(:first-child) {
                margin: 0 0 0 36px;
            } 
            width: 32px;
            height: 20px;
        }
    }

    .nav-item {
        display: flex;
        flex-direction: column;
        color: #666;
        font-weight: 400;
        &__body {
            display: flex;
            align-items: center;
            cursor: pointer;
        }
        &__title {
            margin: 0 0 10px 0;
            letter-spacing: 2px;
            text-transform: uppercase;
            font-weight: 700;
        }
        &__link {
            line-height: 30px;
            color: #666;
            letter-spacing: .4px;
            font-size: 14px;
        }
        &__image-wrapper {
            width: 17px;
            height: 17px;
            border-radius: 50%;
            border: 1px solid #f8f8f8;
            box-shadow: 0 0 0 1px #ddd;
            margin: 0 7px;
        }
        &__image {
            width: 15px;
            height: 15px;
          
        }
        &__text {
            color: #666;
            letter-spacing: .4px;
        }
        &__button {
            border: none;
            background: transparent;
            text-transform: uppercase;
            font-weight: 900;
            color: #777;
            cursor: pointer;
            &::before {
                content: '|';
                color: #999;
                margin: 0 5px 0 0;
            }
        }
    }   

</style>