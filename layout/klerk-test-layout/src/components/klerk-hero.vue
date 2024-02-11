<template>
    <section class="hero">
        <h2 class="hero-title">Выберите рассылки, которые подходят именно вам</h2>
        <Form />
        <Mailings />
    </section>
</template>
<script>
import Form from '@/components/hero-form.vue';
import Mailings from '@/components/hero-mailings.vue';

export default {
    components: {
        Form,
        Mailings,
    }
}
</script>
<style scoped>
.hero {
    max-width: 78.71%;
    margin: 0 auto;
    margin-top: 16px;
    padding: 48px 24px;
    border-radius: 16px;
    background: #F5F5F8;
}

.hero-title {
    margin: 0 auto;
    font-family: Roboto;
    font-size: 24px;
    font-weight: 600;
    line-height: 32px;
    letter-spacing: -0.01em;
    text-align: center;
}

@media(max-width: 900px) {
    .hero {
        padding: 32px 16px;
    }
}

@media(max-width: 600px) {
    .hero {
        max-width: 100%;
    }

    .hero-title {
        text-align: left;
    }
}
</style>