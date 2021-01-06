<template>
  <div id="app">
    <NavBar />
    <Hero :hero="hero" />
  </div>
</template>

<script>
import NavBar from '@/components/NavBar'
import Hero from '@/components/Hero'

export default {
  name: 'App',
  components: {
    NavBar,
    Hero,
  },
  data() {
    return {
      hero: {
        title: 'Chief Tax Judge, MN, Rte.s',
        name: 'George Perez',
        description: `Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy
        eirmod tempor invidunt ut labore et dolore magna aliquyam erat.`,
        altTag: 'Image of George Perez at a Courtroom',
        image: require('../src/assets/hero.jpg'),
        // webp: require('../assets/images/iss_tracker/thumbnail.webp'),
      },
    }
  },
}
</script>

<style lang="scss">
#app {
}
</style>
