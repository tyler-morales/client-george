<template>
  <footer class="footer container">
    <hr />
    <div class="footer__links">
      <a href="#"><span class="logo">George Perez</span></a>
      <a href="#history">Career History</a>
      <a href="#awards">Awards</a>
      <a href="#interests">Interests</a>
    </div>
    <h3 class="created">
      Designed & Developed by
      <a href="https://tmo.codes/" target="_blank" rel="noreferrer">Tyler Morales</a>
    </h3>
  </footer>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.footer {
  width: 100%;

  &__links {
    display: flex;
    margin: 30px 0 50px 0;
    gap: 50px;
    flex-wrap: wrap;

    @include breakpoint(sm) {
      gap: 20px;
    }

    .logo {
      font-weight: 700;
      padding: 10px 20px;
      color: var(--white);
      background-color: var(--color-primary);

      @include breakpoint(sm) {
        background-color: inherit;
        color: black;
        padding: 0;
      }
    }
  }

  .created {
    font-size: 12px;
    font-weight: 200;
    text-align: center;
  }
}
</style>
