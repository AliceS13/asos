<template>
    <div class="login">
        <div class="login__nav">
            <div class="login__nav-header nav-header">
                <div class="nav-header__links">
                    <a class="nav-header__link" v-for="(headerLink, index) in loginHeaderLinks" :key="index" :href="headerLink.link"> {{ headerLink.linkName }} </a>
                </div>
                <div class="close">
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
</template>

<script>
import ImageSvgWrapper from '@/components/global/ImageSvgWrapper'

export default {
    name: 'LoginMenu', 
    components: { ImageSvgWrapper },
    data() {
        return {
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
    .login {
        font-weight: 400;
        position: absolute;
        right: 0;
        top: 54px;
        width: 325px;
        border: 1px solid #ddd;
        z-index: 5;
        // transform: translateY(-100%);
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
            // &:not(:first-child) {
            //     &::before {
            //         content: '|';
            //         padding: 0 8px 0 0;
            //     }
            // }
        }
    }
    .close {
        cursor: pointer;
        width: 19px;
    }
</style>