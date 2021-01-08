<template>
  <div class="card-wrap" ref="card">
    <div class="card" :style="cardStyle">
      <div class="card-bg" :style="[cardBgTransform, cardBgImage]"></div>
      <div class="card-info">
        <slot name="header"></slot>
        <slot name="content"></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['dataImage'],
  computed: {
    cardBgImage() {
      return {
        backgroundImage: `url(${this.dataImage})`,
      }
    },
  },
}
</script>

<style lang="scss" scoped>
$hoverEasing: cubic-bezier(0.23, 1, 0.32, 1);
$returnEasing: cubic-bezier(0.445, 0.05, 0.55, 0.95);

p {
  line-height: 1.5em;
}

h1 + p,
p + p {
  margin-top: 10px;
}

.card-container {
  padding: 40px 80px;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.card-wrap {
  @media (hover: none) {
    .card-info {
      transform: translateY(0);
    }
    .card-info p {
      opacity: 1;
    }
  }

  &:hover {
    .card-info {
      transform: translateY(0);
    }
    .card-info p {
      opacity: 1;
    }
    .card-info,
    .card-info p {
      transition: 0.6s $hoverEasing;
    }
    .card-info:after {
      transition: 5s $hoverEasing;
      opacity: 1;
      transform: translateY(0);
    }
    .card-bg {
      transition: 0.6s $hoverEasing, opacity 5s $hoverEasing;
      opacity: 0.8;
    }
    .card {
      transition: 0.6s $hoverEasing, box-shadow 2s $hoverEasing;
      box-shadow: var(--shadow-md);
    }
  }
}

.card {
  position: relative;
  flex: 0 0 240px;
  width: 240px;
  height: 320px;
  background-color: #333;
  overflow: hidden;
  border-radius: 10px;
  box-shadow: var(--shadow-light);
  transition: 1s $returnEasing;
}

.card-bg {
  opacity: 0.5;
  position: absolute;
  width: 100%;
  height: 100%;
  padding: 20px;
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
  transition: 1s $returnEasing, opacity 5s 1s $returnEasing;
  pointer-events: none;
}

.card-info {
  padding: 20px;
  position: absolute;
  bottom: 0;
  color: #fff;
  transform: translateY(40%);
  transition: 0.6s 1.6s cubic-bezier(0.215, 0.61, 0.355, 1);

  p {
    opacity: 0;
    text-shadow: rgba(black, 1) 0 2px 3px;
    transition: 0.6s 1.6s cubic-bezier(0.215, 0.61, 0.355, 1);
  }

  // * {
  //   position: relative;
  //   z-index: 1;
  // }

  &:after {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    z-index: 0;
    width: 100%;
    height: 100%;
    background-image: linear-gradient(
      to bottom,
      transparent 0%,
      rgba(#000, 0.6) 100%
    );
    background-blend-mode: overlay;
    opacity: 0;
    transform: translateY(100%);
    transition: 1s 1s $returnEasing;
  }
}

.card-info h1 {
  font-family: var(--font-body);
  font-size: 32px;
  font-weight: 700;
  text-shadow: rgba(black, 0.5) 0 10px 10px;
  line-height: 1.3em;
}
</style>
