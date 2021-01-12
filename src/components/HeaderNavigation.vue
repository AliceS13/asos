<template>
    <div>
        <div class="header-nav">
            <div>
                <div class="header-nav__icon" @mouseover="showLoginMenu = true">
                    <SvgIcon id="userIcon" />
                </div>
                <transition name="fade" appear>
                    <div class="login" v-if="showLoginMenu" @mouseover="showLoginMenu = true" >
                        <div class="login__nav">
                            <div class="login__nav-header nav-header">
                                <div class="nav-header__links">
                                    <a class="nav-header__link" v-for="(headerLink, index) in loginHeaderLinks" :key="index" :href="headerLink.link"> {{ headerLink.linkName }} </a>
                                </div>
                                <div class="close" @click="showLoginMenu = false">
                                    <ImageSvgWrapper :imageName="closeIcon"/>
                                </div>
                            </div>
                            <div class="login__nav-body nav-body">
                                <div class="nav-body__items">
                                    <div class="nav-body__item" v-for="(loginItem, loginIndex) in loginItems" :key="loginIndex">
                                        <div class="nav-body__item-icon">
                                            <ImageSvgWrapper :imageName="loginItem.loginIcon"/>
                                        </div>
                                        <a class="nav-body__link" :href="loginItem.loginLink.link">
                                            {{ loginItem.loginLink.title }} 
                                        </a>
                                    </div>
                                </div>
                            </div>
                        </div>        
                    </div>
                </transition>
            </div>
            <div class="header-nav__icon">
                <SvgIcon id="savedItemsIcon" />
            </div>
            <div class="header-nav__icon">
                <SvgIcon id="cartIcon" />
            </div>
        </div>
    </div>
</template>

<script>
import SvgIcon from '@/components/global/SvgIcon'
import LoginMenu from '@/components/LoginMenu'
import ImageSvgWrapper from '@/components/global/ImageSvgWrapper'

export default {
    name: 'HeaderNavigation',
    components: {
        SvgIcon, ImageSvgWrapper
    },
    data() {
        return {
            showLoginMenu: false,
             loginHeaderLinks: [
                { link: '#', linkName: 'Sign In' },
                { link: '#', linkName: 'Join' }
            ],
            loginItems: [
                {
                    loginIcon: 'login-user',
                    loginLink: {
                        link: '#', 
                        title: 'My Account'
                    }
                },
                {
                    loginIcon: 'orders',
                    loginLink: {
                        link: '#', 
                        title: 'My Orders'
                    }
                },
                {
                    loginIcon: 'returns',
                    loginLink: {
                        link: '#', 
                        title: 'Returns Information'
                    }
                },
                {
                    loginIcon: 'contacts',
                    loginLink: {
                        link: '#', 
                        title: 'Contact Preferences'
                    }
                }
            ],
            closeIcon: 'close'
        }
    }
}

</script>

<style lang="scss" scoped>
.header-nav {
        display: flex;
        align-items: center;
        position: relative;
        &__icon {
            padding: 12px 15px;
            cursor: pointer;
        }
    }

.login {
        font-weight: 400;
        position: absolute;
        right: 0;
        top: 54px;
        width: 325px;
        border: 1px solid #ddd;
        z-index: 5;
        &__nav {
            display: flex;
            flex-direction: column;
        }
        &__nav-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: #eee;
            padding: 15px;
        }
        &__nav-body {
            background: #fff;
            padding: 10px 20px;
        }
    }

    .nav-body {
        &__item-icon {
            width: 20px;
            height: 20px;
            margin: 0 15px 0 0;
        }
        &__item {
            display: flex;
            align-items: center;
            &:not(:last-child) {
                margin: 0 0 20px 0;
            }
        }
        &__link {
            color: #2d2d2d;
            font-size: 16px;
            display: inline-block;
        }
    }

    .nav-header {
        &__link {
            letter-spacing: .4px;
            color: #666;
            text-decoration: underline;
            padding: 0 16px 0 0;
        }
    }
    .close {
        cursor: pointer;
        width: 19px;
    }
    
    .fade-enter-active, 
    .fade-leave-active {
         transition: all .2s ease-out;
     }
    .fade-enter,
    .fade-leave-to {
        opacity: 0;
    }

</style>

