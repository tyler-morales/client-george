<template>
  <div id="app">
    <NavBar />
      <Hero :hero="hero" />
    <main>
      <History :history="history" />
      <Awards :awards="awards" />
      <Quote :quote="quote" />
    </main>
  </div>
</template>

<script>
import NavBar from '@/components/NavBar'
import Hero from '@/components/Hero'
import History from '@/components/History'
import Awards from '@/components/Awards'
import Quote from '@/components/Quote'

export default {
  name: 'App',
  components: {
    NavBar,
    Hero,
    History,
    Awards,
    Quote
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
      awards: {
        first: {
          name: 'National Tax Judge of the Year',
          year: '2003',
        },
        second: {
          name: 'Certificate of Commendation | Governor Ventura',
          year: '2002',
        },
        third: {
          name: 'Service Award | Minnesota Hispanic Bar Association',
          year: '2003',
        },
        list: [
          'Certificate of Commendation, Governor Carlson, 1998',
          'Outstanding Mentor of the Year Award, Ramsey County Bar Association, 1999',
          'Outstanding Leadership and Service Award, Minnesota Hispanic Bar Association, 1998',
          'Outstanding Service to Students Award, Hamline University School of Law',
          'Outstanding Leadership and Service Award, Minnesota Hispanic Bar Association, 1998',
          'Outstanding Service, Urban Youth Intern Initiative Program',
          'International Moot Court',
          'President’s Award, Minnesota State Bar Association, 2006',
          'President’s Award, Minnesota State Bar Association, 2003',
          'Volunteer Award, Minnesota State Bar Association, 2000',
          'Wiggins Award, University of Wisconsin Law School',
          'International Law Review',
        ],
      },
      quote:{
        author: 'Mark Twain',
        quote: 'Good friends, good books, and a sleepy conscience: this is the ideal life.'
      }
    }
  },
}
</script>

<style lang="scss">
#app {
  main {
    display: grid;
    gap: 200px;

    @include breakpoint(sm) {
      gap: 100px;
    }
  }
}
</style>
