<template>
  <div class="history container">
    <h2>Career History</h2>
    <section class="timeline">
      <ul>
        <li v-for="(info, index) in timeline_data" v-bind:key="index">
          <span></span>
          <div>{{ info.position }}</div>
          <div>{{ info.description }}</div>
          <div class="year">
            <span>{{ info.yearEnd }}</span>
            <span>{{ info.yearStart }}</span>
          </div>
        </li>
      </ul>
    </section>
  </div>
</template>

<script>
export default {
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
$font-color: var(--color-primary);
$dark-blue: #2e4a62;
$light-blue: #ffda29;

.history {
  justify-self: center;
  max-width: max-content;
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
