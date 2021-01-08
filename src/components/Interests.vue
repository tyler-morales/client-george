<template>
  <div class="interests container">
    <h2>Interests</h2>
    <hr />
    <!-- Card container -->
    <div class="card-container">
      <card
        v-for="(interest, index) in interests.interestList"
        v-bind:key="index"
        :data-image="interest.image"
      >
        <h1 slot="header">{{ interest.name }}</h1>
        <p slot="content">{{ interest.description }}</p>
      </card>
    </div>
  </div>
</template>

<script>
import Card from '@/components/Card'

export default {
  components: { Card },
  props: {
    interests: { type: Object, required: true },
  },
}
</script>

<style lang="scss" scoped>
.interests {
  width: 100%;
}
.card-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  gap: 30px;
  margin: 60px 0;

  @include breakpoint(md) {
    justify-content: center;
  }
  @include breakpoint(sm) {
    margin: 30px 0;
  }
}
</style>
