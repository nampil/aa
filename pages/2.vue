<template>
  <main class="main-container">
    <AppHeader breadcrumb="Propósito de la unidad" />
    <section class="slide2">
      <div class="container">
        <div class="title">
          <h1>Haga clic en las imágenes y lea el texto</h1>
        </div>
        <div class="content">
          <transition
            appear
            name="fade"
          >
            <div class="content-sec left">
              <div class="content-title">
                <h2>¿Qué aprendizajes voy a desarrollar?</h2>
              </div>
              <div class="content-img-button">
                <button
                  aria-label="Click para expandir texto"
                  :class="{btnLeftExpand: btnLeftExpand}"
                  @click="btnLeftExpand = !btnLeftExpand"
                >
                  <img
                    src="@/assets/images/icon-cabeza-left.png"
                    alt="boton para expandir texto"
                  />
                </button>
                <transition name="fade2">
                  <div
                    v-show="btnLeftExpand"
                    class="content-sec-desc"
                  >
                    <p>Reconocer la existencia de normas de comportamiento, en las interacciones realizadas a través de medios de comunicación digital.</p>
                    <p>Al finalizar esta unidad estará en capacidad de:</p>
                    <ul>
                      <li>Describir los principios éticos acerca de la utilización y publicación de información en medios digitales</li>
                      <li>Incorporar reglas de escrituras y comportamuento a partir del reconocimiento de la existencia de un interlocutor humano, en sus interacciones digitales.</li>
                      <li>Establecer paralelos entrre la existencia de estándares éticos de comportamienro de la vida real, que se reflejan en las interacciones digitales</li>
                    </ul>
                  </div>
                </transition>
              </div>
            </div>
          </transition>
          <transition
            appear
            name="fade2"
          >
            <div class="content-sec right">
              <div class="content-title">
                <h2>¿Como aporta esta unidad a mi ciudadanía digital?</h2>
              </div>
              <div class="content-img-button">
                <button
                  aria-label="Click para expandir o colapsar texto"
                  :class="{btnRightExpand: btnRightExpand}"
                  @click="btnRightExpand = !btnRightExpand"
                >
                  <img
                    src="@/assets/images/icon-perso-laptop-right.png"
                    alt="imagen del para expandir o colapsar texto"
                  />
                </button>
                <transition name="fade">
                  <div
                    class="content-sec-desc"
                    v-show="btnRightExpand"
                  >
                    <p>En esta unidad usted aprenderá las normas básicas de comportamienro para usar plataformas digitales. La Etiqueta digital es necesaria para lograr interacciones respetuosas y cordiales en el mundo digital, conservando así un ambiente sano y agradable para todos.</p>
                  </div>
                </transition>
              </div>
            </div>
          </transition>
        </div>
      </div>
    </section>
    <Avance
      class="avance"
      next="3"
      current-page="1"
      total-pages="3"
      prev="/"
    />
  </main>
</template>

<script>
import AppHeader from '@/components/AppHeader'
import Avance from '@/components/Avance'
export default {
  name: 'Slide2',
  components: {
    AppHeader,
    Avance
  },
  data() {
    return {
      btnLeftExpand: false,
      btnRightExpand: false
    }
  },
  computed: {
    avance() {
      return this.$route.name
    }
  }
}
</script>

<style lang="scss" scoped>
.slide2 {
  height: 100%;
}

.title {
  background-color: #fff;
  width: 100%;
  min-height: 50px;
  box-shadow: 3px 5px 10px 0 rgba(0, 0, 0, 0.3);
  padding: 10px;
  margin-bottom: 20px;
  h1 {
    font-size: 1rem;
  }
}
.content {
  flex-grow: 2;
  display: flex;
  flex-direction: column;
  justify-content: center;
  &-title {
    font-size: 0.75rem;
    line-height: 01rem;
    text-align: center;
    color: #2c6387;
  }
}
.content-sec {
  background-color: #f4f4f4;
  padding: 10px 15px;
  margin: 8px;
  text-align: center;
  border-radius: $headerBorderRadius;
  box-shadow: 3px 5px 10px 0 rgba(0, 0, 0, 0.3);
  max-height: 600px;
  overflow-y: auto;
  .content-img-button {
    position: relative;
    width: 100%;
    height: 100%;
    min-height: 300px;
  }
  button {
    position: relative;
    border: none;
    background: none;
    cursor: pointer;
    transform-origin: top center;
    transition: all 0.5s ease-out;
    margin: 5px auto 40px;
    z-index: 1;

    img {
      width: 100%;
      height: auto;
    }
    &.btnLeftExpand,
    &.btnRightExpand {
      transform: scale(0.25);
    }
  }
  .content-sec-desc {
    position: absolute;
    top: 70px;
    text-align: left;
    padding-top: 20px;
    font-size: 0.8rem;
    line-height: 1rem;
    ul {
      padding-left: 20px;
    }
  }
}

@media (min-width: 768px) {
  .container {
    padding-left: 50px;
    padding-top: 50px;
    height: 100%;
    display: flex;
    flex-direction: column;
  }
  .title {
    width: 75%;
    margin-top: 20px;
    h1 {
      font-size: 1.3rem;
    }
  }
  .content {
    flex-direction: row;
    &-title {
      margin: 10px auto 10px;
    }
  }

  .content-sec {
    width: 50%;
    max-height: 600px;
    overflow: hidden;
    .content-img-button {
    }
    button {
      margin: 10px auto 40px;

      img {
        width: 100%;
        height: auto;
      }
      &.btnLeftExpand,
      &.btnRightExpand {
        transform: scale(0.25);
      }
    }
    .content-sec-desc {
      position: absolute;
      top: 70px;
      text-align: left;
      font-size: initial;
      line-height: initial;
      padding-top: 20px;
      ul {
        padding-left: 20px;
      }
    }
  }
}

.fade-enter-active,
.fade-leave-active {
  transition: all 0.7s;
}
.fade-enter /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
  transform: translateY(150%);
}
.fade-leave-to {
  opacity: 0;
  transform: translateY(150%);
}
.fade2-enter-active,
.fade2-leave-active {
  transition: all 1.3s;
}
.fade2-enter /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
  transform: translateY(150%);
}
.fade2-leave-to {
  opacity: 0;
  transform: translateY(150%);
}
</style>