<template>
  <Menu />
  <router-view/>
  <Footer />
</template>

<script>
import Menu from '@/components/Menu.vue'
import Footer from '@/components/Footer.vue'

export default {
  name: 'App',
  components: {
    Menu,
    Footer
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;500;600;700;800&display=swap');

.font-body {
    font-family: Open Sans,sans-serif;
}
</style>
