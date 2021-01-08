<template>
  <div id="app">
    <NavBar />
    <Hero :hero="hero" />
    <main>
      <div class="gap">
        <History :history="history" />
        <Awards :awards="awards" />
      </div>
      <div class="no-gap">
        <Quote :quote="quote" />
        <Stats :stats="stats" />
      </div>
      <div class="gap">
        <Interests :interests="interests" />
        <Footer :footer="footer" />
      </div>
    </main>
  </div>
</template>

<script>
import NavBar from '@/components/NavBar'
import Hero from '@/components/Hero'
import History from '@/components/History'
import Awards from '@/components/Awards'
import Quote from '@/components/Quote'
import Stats from '@/components/Stats'
import Interests from '@/components/Interests'
import Footer from '@/components/Footer'

export default {
  name: 'App',
  components: {
    NavBar,
    Hero,
    History,
    Awards,
    Quote,
    Stats,
    Interests,
    Footer
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
      quote: {
        author: 'Mark Twain',
        quote:
          'Good friends, good books, and a sleepy conscience: this is the ideal life.',
      },
      stats: {
        statList: [
          {
            number: '100+',
            name: 'Talks/ Presentations',
          },
          {
            number: '30',
            name: 'Years in Law',
          },
          {
            number: '17',
            name: 'Years as Chief Judge',
          },
          {
            number: '358',
            name: 'Court Cases',
          },
        ],
        backgroundImage: require('../src/assets/courthouse.jpg'),
      },
      interests: {
        interestList: [
          {
            name: 'Golf',
            description: 'I like golf and to golf is to like me!',
            image: require('../src/assets/hero.jpg'),
          },
          {
            name: 'ABA Conferences',
            description: 'I like golf and to golf is to like me!',
            image: require('../src/assets/hero.jpg'),
          },
          {
            name: 'Life Long Learning',
            description: 'I like golf and to golf is to like me!',
            image: require('../src/assets/hero.jpg'),
          },
        ],
      },
    }
  },
}
</script>

<style lang="scss">
#app {
  .gap {
    display: grid;
    gap: 200px;

    @include breakpoint(sm) {
      gap: 100px;
    }
  }

  .no-gap {
    margin: 200px 0;

    @include breakpoint(sm) {
      margin: 100px 0;
    }
  }
}
</style>
