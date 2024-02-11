<template>
  <div class="container">
    <Header />
    <Hero />
    <Footer />
  </div>
</template>
<script>
import Header from '@/components/klerk-header.vue';
import Hero from '@/components/klerk-hero.vue';
import Footer from '@/components/klerk-footer.vue'

export default {
  components: {
    Header,
    Hero,
    Footer,
  }
}
</script>
<style scoped>
.container {
  margin-top: 48px;
}
</style>