<template>
    <ul class="nav">
        <li class="nav-item nav-item__active">Рассылки</li>
        <li class="nav-item">Соцсети</li>
        <li class="nav-item">Мессенджеры</li>
    </ul>
</template>
<style scoped>
.nav {
    margin-top: 24px;
    display: flex;
    justify-content: center;
    align-items: center;
}
.nav-item {
    position: relative;
    font-family: Roboto;
    font-size: 16px;
    font-weight: 400;
    line-height: 24px;
    letter-spacing: 0px;
    text-align: left;
    cursor: pointer;
    transition: .3s linear;
}

.nav-item:not(:last-child) {
    position: relative;
    margin-right: 24px;
}
.nav-item__active,
.nav-item:hover {
    color: #5A8CF1;
    transition: .3s linear;
}

.nav-item:active {
    opacity: 0.5;
}
.nav-item__active::after {
    position: absolute;
    display: block;
    height: 2px;
    content: '';
    left: 0;
    right: 0;
    bottom: -16px;
    background-color: #5A8CF1;
}
</style>