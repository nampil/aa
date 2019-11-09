<template>
  <div class="main-wrapper">
    <div class="inner-wrapper">
      <a
        class="skip-main"
        href="#main"
      >Saltar al contenido principal</a>
      <nuxt
        id="main"
        aria-live="assertive"
        ref="routerView"
      />
    </div>
  </div>
</template>
<script>
import AppHeader from '@/components/AppHeader'
export default {
  components: {
    AppHeader
  }
}
</script>

<style lang="scss">
.main-wrapper {
  position: relative;
  width: 100vw;
  background-color: #fff;
  background-image: url('../assets/images/fondo.png');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  margin: auto;
}

@media (min-width: 992px) {
  .inner-wrapper {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    padding: 10px;
  }
  .main-wrapper {
    padding-top: 56.22%;
    max-width: 1366px;
  }
}
</style>
