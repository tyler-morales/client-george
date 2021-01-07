<template>
  <section class="stats" :style="imageStyleObject">
    <h2>Career Stats</h2>
    <ul class="stat-box container">
      <li
        v-for="(stat, index) in stats.statList"
        v-bind:key="index"
        class="stat"
        :class="gray"
      >
        <span class="stat--number">{{ stat.number }}</span>
        <span class="stat--name">{{ stat.name }}</span>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  props: {
    stats: { type: Object, required: true },
  },
  computed: {
    imageStyleObject() {
      return {
        backgroundImage: `linear-gradient(180deg, rgba(38,48,86,0.5) 0%, rgba(38,48,86,1) 100%), url(${this.stats.backgroundImage})`,
        backgrountRepeat: 'no-repeat',
        backgroundSize: 'cover',
        backgroundPosition: 'center',
      }
    },
  },
}
</script>

<style lang="scss" scoped>
.stats {
  padding: 100px 30px;

  h2 {
    max-width: 1100px;
    margin: calc(12px + 1.05vw) auto;
  }

  .stat-box {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    justify-items: center;
    gap: 100px;
    text-align: center;
    border: 2px solid var(--color-quatary);
    padding: 30px 80px;
    width: auto;

    @include breakpoint(md) {
      grid-template-columns: 1fr;
      width: 100%;
      padding: 30px 60px;
    }

    @include breakpoint(sm) {
      gap: 40px;
      padding: 0;
      border: 0;
    }

    li:nth-child(1) {
      color: var(--color-secondary);
    }

    li:nth-child(2) {
      color: var(--color-quatary);
    }
    li:nth-child(3) {
      color: var(--color-quatary);

      @include breakpoint(md) {
        color: var(--color-secondary);
      }
    }

    li:nth-child(4) {
      color: var(--color-secondary);

      @include breakpoint(md) {
        color: var(--color-quatary);
      }
    }

    .stat {
      display: flex;
      flex-direction: column;

      &--number {
        font-size: 140px;
        line-height: 140px;

        @include breakpoint(xs) {
          font-size: 120px;
          line-height: 120px;
        }
      }

      &--name {
        font-size: 27px;
      }
    }
  }
}
</style>
