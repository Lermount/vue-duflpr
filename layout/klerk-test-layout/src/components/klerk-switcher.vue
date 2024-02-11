<template>
    <input class="switcher" type="checkbox" />
</template>
<style scoped>
.switcher {
    position: relative;
    margin-right: 8px;
    width: 32px;
    height: 16px;
    border-radius: 100px;
    background: #DCDCDC;
    appearance: none;
    transition: 0.3s;
}

.switcher:checked {
    background: #316FEE;
}

.switcher:focus {
    outline-color: #316FEE;
}

.switcher::before {
    content: '';
    position: absolute;
    top: 1px;
    left: 1px;
    width: 14px;
    height: 14px;
    border-radius: 50%;
    background-color: #fff;
    cursor: pointer;
    transition: 0.3s;
}

.switcher:checked:before {
    left: 17px;
}
</style>