<template>
    <ul class="breadcrumbs">
        <li class="breadcrumbs-item">Главная</li>
        <li class="breadcrumbs-icon"></li>
        <li class="breadcrumbs-item">Рассылки</li>
        <li class="breadcrumbs-icon"></li>
        <li class="breadcrumbs-item">Хлебные крошки</li>
    </ul>
</template>
<style scoped>
.breadcrumbs {
    margin-top: 28px;
    display: flex;
    align-items: center;
    justify-content: center;
}

.breadcrumbs-item {
    font-family: Roboto;
    font-size: 13px;
    font-weight: 400;
    line-height: 16px;
    letter-spacing: 0px;
    text-align: left;
    color: #999999;
    cursor: pointer;
    border-bottom: 1px solid #E6EDFF;
    transition: .3s linear;
}

.breadcrumbs-item:hover {
    color: #5A8CF1;
    border-color: #5A8CF1;
    transition: .3s linear;
}

.breadcrumbs-item:active {
    opacity: 0.5;
}

.breadcrumbs-icon {
    margin: 0px 8px;
    width: 13px;
    height: 16px;
    background-repeat: no-repeat;
    background-position: center;
    background-size: contain;
    background-image: url("data:image/svg+xml,%3Csvg width='10' height='4' viewBox='0 0 10 4' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M7.327 3.575C7.457 3.29767 7.58267 3.055 7.704 2.847C7.834 2.639 7.95967 2.46567 8.081 2.327H0.502V1.781H8.081C7.95967 1.63367 7.834 1.456 7.704 1.248C7.58267 1.04 7.457 0.801666 7.327 0.533H7.782C8.328 1.16567 8.9 1.63367 9.498 1.937V2.171C8.9 2.46567 8.328 2.93367 7.782 3.575H7.327Z' fill='%23999999'/%3E%3C/svg%3E%0A");
}
</style>