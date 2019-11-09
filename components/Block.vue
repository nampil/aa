<template>
  <div :class="['block', {heading: heading} ]">
    <h1 v-if="heading">{{text}}</h1>
    <h2 v-else>{{text}}</h2>
  </div>
</template>

<script>
export default {
  name: 'block',
  props: ['text', 'heading']
}
</script>

<style lang="scss" scoped>
.block {
  border: 2px solid $green;
  padding: 6px 12px;
  border-radius: 8px;
  margin: 6px 12px;
  font-weight: 900;
  position: relative;
  background-color: $gris;
  text-align: center;

  &::before,
  &::after {
    content: '';
    display: block;
    position: absolute;
    width: 70%;
    height: 4px;
    background-color: $green;
    top: -4px;
    left: 50%;
    transform: translateX(-50%);
    border-radius: 999px;
  }
  &::after {
    top: 100%;
  }
  &.heading {
    border-color: $morado;
    &::before,
    &::after {
      background-color: $morado;
    }
  }
}

@media (min-width: 768px) {
  .block {
    display: inline;
  }
}
</style>