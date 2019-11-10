<template>
  <main>
    <AppHeader
      breadcrumb="Unidad 3: Nuevos lenguajes, nuevos problemas de comunicación"
      subBreadcrumb="Para Saber: Nuevos lenguajes, nuevos problemas de comunicación"
    />
    <section class="slide6">
      <div class="container">
        <div class="content">
          <div class="video">
            <iframe
              width="1000"
              height="562"
              src="https://www.youtube.com/embed/bs9gYcirRAM"
              frameborder="0"
              allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen
            ></iframe>
          </div>
        </div>
      </div>
    </section>
    <Avance
      class="avance"
      next="7"
      currentPage="2"
      totalPages="28"
      prev="5"
    />
  </main>
</template>

<script>
import Avance from '@/components/Avance'
import AppHeader from '@/components/AppHeader'
export default {
  components: {
    Avance,
    AppHeader
  }
}
</script>

<style lang="scss" scoped>
.slide6 {
  //height: 100%;
  //min-height: 80vh;
  //overflow: hidden;
  //margin-bottom: 30px;
}
.container {
  height: 100%;
  min-height: 80vh;
  align-items: center;
  justify-content: center;
}
.content {
  width: 100%;
  //height: 100%;
  max-width: 600px;
}
.video {
  position: relative;
  padding-bottom: 56.25%; /* 16:9 */
  padding-top: 25px;
  height: 0;
  width: 100%;

  iframe {
    background-color: $gris;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }
}

@media (min-width: 768px) {
  .slide6,
  .container,
  .content {
    height: unset;
    min-height: unset;
  }
  .container {
    padding-top: 120px;
    padding-bottom: 60px;
  }
}
@media (min-width: 992px) {
}
</style>