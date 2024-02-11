<template>
    <ul class="mailings">
        <Link v-for="link in mailings" :key="link.id" :link="link" />
    </ul>
</template>
<script>
import { mailings } from '@/data/mailings';
import Link from '@/components/hero-link.vue';

export default {
    components: { Link },

    computed: {
        mailings() {
            return mailings
        }
    }
}
</script>
<style scoped>
.mailings {
    margin-top: 32px;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-template-rows: repeat(2, 1fr);
    gap: 24px;
}

@media(max-width: 900px) {
    .mailings {
        margin-top: 24px;
        grid-template-columns: repeat(1, 1fr);
        grid-template-rows: repeat(4, 1fr);
    }
}
</style>