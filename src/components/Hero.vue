<template>
  <div class="hero container">
    <div class="hero__text">
      <span class="hero__text--title">{{ hero.title }}</span>
      <h1 class="hero__text--name">{{ hero.name }}</h1>
      <p class="hero__text--description">{{ hero.description }}</p>
    </div>
    <picture class="hero--img">
      <source type="image/webp" :srcset="hero.webp" />
      <img :src="hero.image" :alt="hero.altTag" />
    </picture>
  </div>
</template>

<script>
export default {
  props: {
    hero: { type: Object, required: true },
  },
}
</script>

<style lang="scss" scoped>
.hero {
  display: grid;
  place-items: center;
  height: 90vh;
  gap: 100px;
  grid-template-columns: 2fr 1fr;

  @include breakpoint(md) {
    height: auto;
    grid-template-columns: 1fr;
    gap: 30px;
    margin-top: 30px;
    text-align: center;
  }

  &__text {
    &--title {
      margin-bottom: 10px;
      display: block;
    }
    &--name {
      font-family: var(--font-display);
      font-size: 48px;

      @include breakpoint(md) {
        font-size: 36px;
      }
    }
    &--description {
    }
  }

  &--img {
    max-width: 400px;
  }
}
</style>
