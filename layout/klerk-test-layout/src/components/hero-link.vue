<template>
    <li class="card">
        <div class="card-top">
            <div class="card-top-left">
                <p class="card-name"> {{ link.name }}</p>
                <h3 class="card-title"> {{ link.title }}</h3>
                <p class="card-description">{{ link.description }}</p>
            </div>
            <img v-if="link.id == 1" class="card-top-right" src="../../public/images/icon1.webp" alt="card-logo">
            <img v-if="link.id == 2" class="card-top-right" src="../../public/images/icon2.webp" alt="card-logo">
            <img v-if="link.id == 3" class="card-top-right" src="../../public/images/icon3.webp" alt="card-logo">
            <img v-if="link.id == 4" class="card-top-right" src="../../public/images/icon4.webp" alt="card-logo">
        </div>

        <div class="card-bottom">
            <p class="card-check" :class="{ 'card-check_bold': link.id == 4 }">
                <i class="card-check-icon"></i>
                {{ link.contentFirst }}
            </p>
            <p class="card-check">
                <i class="card-check-icon"></i>
                {{ link.contentSecond }}
            </p>

            <div class="switcher-content">
                <Switcher class="switcher" />
                <p class="switcher-description">{{ link.clients }}</p>
            </div>
        </div>
    </li>
</template>
<script>
import Switcher from '@/components/klerk-switcher.vue';

export default {
    props: ['link'],
    components: { Switcher }
}
</script>
<style scoped>
.card {
    display: flex;
    flex-direction: column;
    padding: 24px;
    border-radius: 16px;
    box-shadow: 0px 8px 16px 0px #00000014;
    background-color: #fff;
}

.card-top {
    display: flex;
    justify-content: space-between;
}

.card-top-left {
    margin-right: 24px;
}

.card-name {
    font-family: Roboto;
    font-size: 13px;
    font-weight: 400;
    line-height: 16px;
    letter-spacing: 0px;
    text-align: left;
    color: #999999;
}

.card-title {
    margin-top: 0;
    margin-bottom: 8px;
    font-family: Roboto;
    font-size: 20px;
    font-weight: 600;
    line-height: 28px;
    letter-spacing: 0px;
    text-align: left;
    color: #000;
}

.card-description {
    font-family: Roboto;
    font-size: 14px;
    font-weight: 400;
    line-height: 20px;
    letter-spacing: 0px;
    text-align: left;
    color: #666;
    max-width: 324px;
}

.card-top-right {
    width: 80px;
    height: 80px;
}

.card-bottom {
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    height: 100%;
    margin-top: 16px;
}

.card-check {
    margin-top: auto;
    margin-bottom: 8px;
    display: flex;
    align-items: center;
    font-family: Roboto;
    font-size: 14px;
    font-weight: 400;
    line-height: 20px;
    letter-spacing: 0px;
    text-align: left;
    color: #000;
}

.card-check-icon {
    width: 16px;
    height: 12.2px;
    margin-right: 8px;
    background-repeat: no-repeat;
    background-size: contain;
    background-position: center;
    background-image: url("data:image/svg+xml,%3Csvg width='16' height='13' viewBox='0 0 16 13' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M5.08471 9.62365L1.93292 6.47186C1.57839 6.11733 1.00389 6.11631 0.648103 6.46959C0.290537 6.82464 0.289516 7.40265 0.645826 7.75896L5.08471 12.1978L15.3586 1.92397C15.7128 1.56972 15.7128 0.995371 15.3586 0.641122C15.0044 0.286991 14.4303 0.286855 14.076 0.640819L5.08471 9.62365Z' fill='%2300CC33'/%3E%3C/svg%3E%0A");
}

.card-check_bold {
    font-weight: 600;
}

.switcher-content {
    margin-top: 16px;
    display: flex;
    align-items: center;
}

.switcher {
    width: 48px;
    height: 24px;
}

.switcher::before {
    width: 22px;
    height: 22px;
}

.switcher:checked:before {
    left: 25px;
}

.switcher-description {
    font-family: Roboto;
    font-size: 14px;
    font-weight: 400;
    line-height: 20px;
    letter-spacing: 0px;
    text-align: left;
    color: #000;
}

@media(max-width: 600px) {

    .card {
        padding: 24px 16px;
    }

    .card-top {
        position: relative;
    }

    .card-top-left {
        margin-right: 0;
    }
    .card-top-right {
        position: absolute;
        width: 40px;
        height: 40px;
        top: 0;
        right: 0;
    }

    .card-description {
        max-width: 311px;
    }
}
</style>