<template>
  <nav>
    <div class="nav-container">
      <div class="nav">
        <a href="#"><span class="logo">George Perez</span></a>
        <button @click="isOpen = !isOpen">
          <svg
            v-if="!isOpen"
            class="menu"
            viewBox="0 0 30 30"
            width="30px"
            height="30px"
          >
            <path
              d="M 3 7 A 1.0001 1.0001 0 1 0 3 9 L 27 9 A 1.0001 1.0001 0 1 0 27 7 L 3 7 z M 3 14 A 1.0001 1.0001 0 1 0 3 16 L 27 16 A 1.0001 1.0001 0 1 0 27 14 L 3 14 z M 3 21 A 1.0001 1.0001 0 1 0 3 23 L 27 23 A 1.0001 1.0001 0 1 0 27 21 L 3 21 z"
            />
          </svg>
          <svg
            v-if="isOpen"
            class="menu"
            viewBox="0 0 50 50"
            width="30px"
            height="30px"
          >
            <path
              d="M 40.783203 7.2714844 A 2.0002 2.0002 0 0 0 39.386719 7.8867188 L 25.050781 22.222656 L 10.714844 7.8867188 A 2.0002 2.0002 0 0 0 9.2792969 7.2792969 A 2.0002 2.0002 0 0 0 7.8867188 10.714844 L 22.222656 25.050781 L 7.8867188 39.386719 A 2.0002 2.0002 0 1 0 10.714844 42.214844 L 25.050781 27.878906 L 39.386719 42.214844 A 2.0002 2.0002 0 1 0 42.214844 39.386719 L 27.878906 25.050781 L 42.214844 10.714844 A 2.0002 2.0002 0 0 0 40.783203 7.2714844 z"
            />
          </svg>
        </button>
      </div>
      <div :class="isOpen ? 'show' : 'hide'" class="nav__links">
        <a href="#">About</a>
        <a href="#">Awards</a>
        <a href="#">Career History</a>
        <a href="#">Interests</a>
      </div>
    </div>
  </nav>
</template>

<script>
import logo from '../assets/popye-icon.svg'

export default {
  data() {
    return {
      logo: logo,
      isOpen: false,
    }
  },
}
</script>

<style lang="scss" scoped>
nav {
  display: flex;
  background-color: var(--color-primary);

  @include breakpoint(sm) {
    display: block;
  }
}

.nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  color: var(--white);
  padding: 1em 2em;
  font-weight: 100;

  @include breakpoint(sm) {
    width: 100%;
  }

  .logo {
    font-weight: 700;
  }

  .menu {
    background: none;
    fill: white;
    display: none;

    @include breakpoint(sm) {
      display: block;
    }
  }

  &__links {
    display: flex;
    align-items: center;
    gap: 25px;
    color: var(--white);
    font-size: 15px;
    font-weight: 200;
    padding: 1em 2em;

    @include breakpoint(sm) {
      flex-direction: column;
      align-items: self-start;
    }
  }
}
.show {
  display: flex;
}

.hide {
  display: none;
}

@media screen and (min-width: 600px) {
  .nav__links {
    display: flex;
  }
}
</style>
