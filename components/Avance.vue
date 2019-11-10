<template>
  <section>
    <div class="wrapper">
      <h1>Mi Avance</h1>
      <nav>
        <div
          v-if="prev"
          class="prev"
        >
          <button
            aria-label="anterior"
            @click="moveBack"
          >
            <img
              src="@/assets/images/prev.svg"
              alt="Boton anterior"
            />
          </button>
        </div>
        <div class="pages">{{currentPage}}/{{totalPages}}</div>
        <div
          v-if="next"
          class="next"
        >
          <button
            aria-label="siguiente"
            @click="moveForward"
          >
            <img
              aria-hidden="true"
              src="@/assets/images/next.svg"
              alt="Boton siguiente"
            />
          </button>
        </div>
      </nav>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Avance',
  props: ['prev', 'currentPage', 'totalPages', 'next'],
  methods: {
    moveForward() {
      if (this.next === '/') {
        this.$router.push(this.next)
      } else {
        this.$router.push(`/${this.next}`)
      }
    },
    moveBack() {
      if (this.prev === '/') {
        this.$router.push('/')
      } else {
        this.$router.push(`/${this.prev}`)
      }
    }
  }
}
</script>

<style scoped lang="scss">
//Styles in main.scss
</style>