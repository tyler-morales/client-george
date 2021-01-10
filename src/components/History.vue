<template>
  <div id="history" class="history container">
    <h2 data-aos="fade-up">Career History</h2>
    <hr data-aos="fade-up" />
    <section class="timeline">
      <ul>
        <li
          v-for="(info, index) in timeline_data"
          v-bind:key="index"
          data-aos="fade-up"
        >
          <span></span>
          <div>{{ info.position }}</div>
          <div>{{ info.description }}</div>
          <div class="year">
            <span>{{ info.yearStart }}</span>
            <span>{{ info.yearEnd }}</span>
          </div>
        </li>
      </ul>
    </section>

    <!-- Court Case Btn -->
    <div class="court-cases" data-aos="fade-up">
      <a :href="history.link" target="_blank">Court Cases</a>
      <span>View all court cases from the MN. tax court</span>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    history: { type: Object, required: true },
  },
  data: () => {
    return {
      timeline_data: [
        {
          position: 'Oberline College',
          yearStart: '1979',
          yearEnd: '1983',
        },
        {
          position: 'Immigration Attorney Centro Legal',
          yearStart: '1983',
          yearEnd: '1987',
        },
        {
          position: 'Associate, Litigation, Kasdorf, Lewis, Swietlik',
          // description: 'Sobrecary St, Tagum City',
          yearStart: '1987',
          yearEnd: '1989',
        },
        {
          position: 'Law Clerk, Judge Susan Steingass, Circuit Court',
          yearStart: '1989',
          yearEnd: '1990',
        },
        {
          position: 'Immigration Attorney Centro Legal',
          yearStart: '1991',
          yearEnd: '1992',
        },
        {
          position: 'U.S. Tax Attorney, Department of the Treasury',
          yearStart: '1992',
          yearEnd: '1995',
        },
        {
          position: 'Judge, Minnesota Tax Court',
          yearStart: '1995',
          yearEnd: '1997',
        },
        {
          position: 'Chief Judge, Minnesota Tax Court',
          yearStart: '1997',
          yearEnd: '2001',
        },
        {
          position: 'Chief Judge, Minnesota Tax Court',
          yearStart: '2001',
          yearEnd: '2013',
        },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
.court-cases {
  margin: 0 auto;
  text-align: center;

  a {
    font-size: 18px;
    background-color: var(--color-primary);
    color: var(--white);
    padding: 10px 20px;
    border-radius: 20px;
    box-shadow: var(--shadow-light);
    border: 3px solid white;
    transition: all 0.3s;

    &:hover {
      box-shadow: var(--shadow-md);
      transform: translateY(3px);
    }

    &:focus {
      border: 2px solid var(--color-primary);
    }
  }
  span {
    display: block;
    font-size: 12px;
    margin-top: 10px;
    color: rgb(112, 112, 112);
  }
}

$font-color: var(--color-primary);
$dark-blue: #2e4a62;
$light-blue: #ffda29;

.history {
  justify-self: center;
  max-width: max-content;
  margin-top: 100px;
}

@mixin clearfix {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
}

@mixin set-border($thickness, $color, $radius) {
  border: $thickness solid $color;
  border-radius: $radius;
}

.timeline {
  // display: flex;

  @include breakpoint(md) {
    // justify-content: center;
  }
  padding: 5px 45px;
  ul {
    position: relative;
    &::before {
      @include clearfix();
      height: 100%;
    }
  }
  li {
    position: relative;
    margin: 60px 35px;
    width: 100%;
    list-style: none;
    line-height: 25px;
    & > span {
      @include clearfix();
      left: -25px;
      height: 110%;
      @include set-border(2px, $font-color, none);
    }
    & > span::before,
    & > span::after {
      @include clearfix();
      width: 14px;
      height: 14px;
      @include set-border(3px, $font-color, 50%);
      left: -10px;
      background: $light-blue;
    }
    & > span::before {
      top: -15px;
    }
    & > span::after {
      top: 100%;
    }
    div {
      &:nth-child(2) {
        font-size: 1.2em;
      }
      &:nth-child(3),
      &:nth-child(4) {
        font-size: 1em;
        color: var(--color-primary);
      }
    }
    .year span {
      position: absolute;
      font-size: 1em;
      left: -85px;
      width: 40px;
      text-align: right;
      &:first-child {
        top: -20px;
      }
      &:last-child {
        top: 100%;
      }
    }
  }
}
</style>
