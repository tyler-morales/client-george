<template>
  <blockquote>
    <p class="quote">{{ quote.quote }}</p>
    <figcaption class="author">–{{ quote.author }}</figcaption>
  </blockquote>
</template>

<script>
export default {
  props: {
    quote: { type: Object, required: true },
  },
  data: () => {},
}
</script>

<style lang="scss" scoped>
blockquote {
  background-color: var(--gray-1);
  text-align: center;
  padding: 80px;

  @include breakpoint(md) {
    padding: 40px;
  }

  .quote {
    font-size: 47px;
    max-width: 50vw;
    line-height: 1.4em;
    font-family: var(--font-display);
    margin: 0 auto;
    font-weight: 400;

    @include breakpoint(md) {
      font-size: 27px;
      max-width: 80vw;
      line-height: 1.4em;
    }
  }

  .author {
    margin-top: 50px;

    @include breakpoint(md) {
      margin-top: 25px;
    }
  }
}
</style>
