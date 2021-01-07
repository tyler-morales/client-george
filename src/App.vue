<template>
  <div id="app">
    <NavBar />
    <main>
      <Hero :hero="hero" />
      <History :history="history" />
    </main>
  </div>
</template>

<script>
import NavBar from '@/components/NavBar'
import Hero from '@/components/Hero'
import History from '@/components/History'

export default {
  name: 'App',
  components: {
    NavBar,
    Hero,
    History,
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
      history: {
        link:
          'https://mn.gov/tax-court/search/?query=george+author%3A%22perez%22+&v%3Asources=mn-tax-court-live&date=&binning-state=&qt=george&author=perez&start-date=&end-date=&sortby=#',
      },
    }
  },
}
</script>

<style lang="scss">
#app {
  main {
    display: grid;
    gap: 100px;
  }
}
</style>
