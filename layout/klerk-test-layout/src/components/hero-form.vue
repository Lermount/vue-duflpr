<template>
    <form action="#" class="hero-form">
        <input class="hero-input" :class="{'hero-input-mobile' : isMobile}" placeholder="Электронная почта" type="email">
        <button class="btn" :class="{'btn-mobile' : isMobile}" type="submit">
            {{ isMobile ? '' : 'Подписаться' }}
            <i v-if="isMobile" class="btn-icon"></i>
        </button>
        <div class="switcher-content">
            <Switcher />
            <p class="swither-description">Подписаться на все рассылки</p>
        </div>
    </form>
</template>
<script>
import Switcher from '@/components/klerk-switcher.vue';

export default {
    components: { Switcher },

    data: () => ({
        screenWidth: 0,
        isMobile: false
    }),

    mounted() {
        this.screenWidth = window.innerWidth;
        window.addEventListener('resize', this.handleResize);
    },

    watch: {
        screenWidth(width) {
            if (width <= 900) {
                this.isMobile = true;
            } else {
                this.isMobile = false;
            }
        },
    },

    methods: {
        handleResize() {
            this.screenWidth = window.innerWidth;
        },
    }
}
</script>
<style scoped>
.hero-form {
    position: relative;
}

.hero-input {
    margin-top: 24px;
    margin-left: 24px;
    margin-right: 24px;
    padding: 0px 190px 0px 16px;
    height: 56px;
    width: calc(100% - 266px);
    border: none;
    border-radius: 16px 100px 100px 16px;
}

.hero-input:focus {
    outline-color: #316FEE;
}

.hero-input::placeholder {
    font-family: Roboto;
    font-size: 16px;
    font-weight: 400;
    line-height: 24px;
    letter-spacing: 0px;
    text-align: left;
}

.hero-input-mobile {
    padding: 0px 70px 0px 16px;
    width: calc(100% - 86px);
    margin-top: 16px;
    margin-left: 0;
    margin-right: 0;
}

.btn {
    position: absolute;
    cursor: pointer;
    top: 24px;
    right: 36px;
    border: none;
    border-radius: 100px;
    padding: 16px 32px;
    background-color: #316FEE;
    font-family: Roboto;
    font-size: 16px;
    font-weight: 400;
    line-height: 24px;
    letter-spacing: 0px;
    text-align: left;
    color: #fff;
    transition: .3s linear;
}

.btn:hover {
    transition: .3s linear;
    background-color: #5A8CF1;
}

.btn:active {
    opacity: 0.8;
}

.btn-mobile {
    top: 16px;
    right: 0;
    padding: 16px;
    border-radius: 100px;
}

.btn-icon {
    display: flex;
    height: 24px;
    width: 24px;
    background-repeat: no-repeat;
    background-position: center;
    background-size: contain;
    background-image: url("data:image/svg+xml,%3Csvg width='24' height='24' viewBox='0 0 24 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M7.34998 17.355L12.6933 12L7.34998 6.645L8.99498 5L15.995 12L8.99498 19L7.34998 17.355Z' fill='white'/%3E%3C/svg%3E%0A");
}

.switcher-content {
    margin-top: 18px;
    margin-left: 24px;
    display: flex;
    align-items: center;
}

.swither-description {
    font-family: Roboto;
    font-size: 14px;
    font-weight: 400;
    line-height: 20px;
    letter-spacing: 0px;
    text-align: left;

}

@media(max-width: 900px) {
    .switcher-content {
        margin-left: 0;
    }
}
</style>