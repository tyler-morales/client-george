<template>
  <div id="awards" class="awards container">
    <h2 data-aos="fade-up">Awards</h2>
    <hr data-aos="fade-up" />
    <section>
      <div class="top-awards" data-aos="fade-up">
        <div class="top-awards__second">
          <span class="name">{{ awards.second.name }}</span>
          <span class="year">{{ awards.second.year }}</span>
        </div>
        <div class="top-awards__main">
          <span class="name">{{ awards.first.name }}</span>
          <span class="year">{{ awards.first.year }}</span>
        </div>
        <div class="top-awards__second">
          <span class="name">{{ awards.third.name }}</span>
          <span class="year">{{ awards.third.year }}</span>
        </div>
      </div>

      <!-- Extra Awards -->
      <div class="extra-awards" data-aos="fade-up">
        <ul v-bind:class="{ 'is-collapsed': collapsed }">
          <li
            v-for="(award, index) in awards.list"
            v-bind:key="index"
            data-aos="fade-up"
          >
            {{ award }}
          </li>
        </ul>
        <button
          v-on:click="collapsed = !collapsed"
          aria-label="Toggle to show awards"
        >
          {{ collapsed ? 'Show More +' : 'Show Less -' }}
        </button>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  props: {
    awards: { type: Object, required: true },
  },
  data: () => {
    return {
      collapsed: true,
    }
  },
}
</script>

<style lang="scss" scoped>
.top-awards {
  display: flex;
  justify-content: center;
  gap: 50px;
  text-align: center;
  color: var(--white);
  margin-top: 60px;

  @include breakpoint(md) {
    flex-wrap: wrap;
  }

  .year {
    display: block;
    background-color: var(--color-primary);
    border-radius: 0 0 10px 10px;
    padding: 5px;
  }
  .name {
    border-radius: 10px 10px 0 0;
    padding: 20px;
    display: block;
    background-color: var(--color-secondary);
  }

  &__main {
    font-size: 24px;

    @include breakpoint(md) {
      width: 100%;
    }
  }

  &__second {
    font-size: 21px;
    transform: translateY(16px);

    @include breakpoint(md) {
      transform: translateY(0);
      width: 100%;
    }
  }
}

.extra-awards {
  display: flex;
  flex-direction: column;

  ul {
    columns: 2 auto;
    column-gap: 60px;
    padding: 60px 0 40px 0;
    max-width: 1200px;

    @include breakpoint(md) {
      columns: 1 auto;
      padding: 20px;
      text-align: center;
    }

    li {
      width: auto;
      list-style-type: disc;
    }
  }

  .is-collapsed {
    li:nth-child(n + 7) {
      display: none;
    }
  }

  button {
    margin: 0 auto;
    font-size: 16px;

    &:focus {
      border: 2px solid var(--color-primary);
    }
  }
}
</style>
