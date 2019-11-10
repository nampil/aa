<template>
  <main>
    <AppHeader breadcrumb="Mapa de aprendizaje" />
    <section class="slide4">
      <div class="container">
        <transition
          appear
          name="fade-fly-right"
        >
          <h1 class="title">Para crecer como ciudadano digital</h1>
        </transition>
        <div class="content">
          <div class="content-inner-wrapper">
            <div class="content-sec">
              <div class="content-sec-imgBtn">
                <div class="content-sec-img">
                  <transition
                    appear
                    name="fade-fly-down"
                  >
                    <img
                      src="@/assets/images/persona-saber.png"
                      alt="Dibujo de Persona con muletas"
                    />
                  </transition>
                </div>
                <transition
                  appear
                  name="fade-fly-up"
                >
                  <button
                    @click="paraSaberBtn"
                    aria-label="Continuar a la sección 'Para Saber'"
                  >
                    <img
                      src="@/assets/images/para-saber-btn.png"
                      alt="Grafico de una computadora"
                    />
                  </button>
                </transition>
              </div>

              <transition
                appear
                name="fade-fly-down"
              >
                <h2
                  style="transition-delay: 0.2s"
                  id="btn-title"
                  class="btn-title delay-2"
                >Para Saber</h2>
              </transition>
            </div>
            <div class="connect-dots">
              <img
                src="@/assets/images/connect-dots1.png"
                alt="Puntos de conección"
              />
            </div>
            <div class="content-sec">
              <div class="content-sec-imgBtn">
                <transition
                  appear
                  name="fade-fly-down"
                >
                  <div
                    style="transition-delay: 0.2s"
                    class="content-sec-img"
                  >
                    <img
                      src="@/assets/images/persona-hacer.png"
                      alt="Dibujo de Persona con muletas"
                    />
                  </div>
                </transition>
                <transition
                  appear
                  name="fade-fly-up"
                >
                  <button
                    style="transition-delay: 0.2s"
                    @click="paraHacerBtn"
                    aria-label="Continuar a la sección 'Para saber hacer'"
                  >
                    <img
                      src="@/assets/images/para-hacer-btn.png"
                      alt="Grafico de una computadora"
                    />
                  </button>
                </transition>
              </div>

              <transition
                appear
                name="fade-fly-down"
              >
                <h2
                  style="transition-delay: 0.4s"
                  id="btn-title"
                  class="btn-title delay-3"
                >Para saber hacer</h2>
              </transition>
            </div>
            <div class="connect-dots">
              <img
                src="@/assets/images/connect-dots2.png"
                alt="Puntos de conección"
              />
            </div>
            <div class="content-sec">
              <div class="content-sec-imgBtn">
                <transition
                  appear
                  name="fade-fly-down"
                >
                  <div
                    style="transition-delay: 0.4s"
                    class="content-sec-img"
                  >
                    <img
                      src="@/assets/images/persona-aplicar.png"
                      alt="Dibujo de Persona con muletas"
                    />
                  </div>
                </transition>
                <transition
                  appear
                  name="fade-fly-up"
                >
                  <button
                    style="transition-delay: 0.4s"
                    @click="paraAplicarBtn"
                    aria-label="Continuar a la sección 'Para aplicar lo que se'"
                  >
                    <img
                      src="@/assets/images/para-aplicar-btn.png"
                      alt="Grafico de una computadora"
                    />
                  </button>
                </transition>
              </div>

              <transition
                appear
                name="fade-fly-down"
              >
                <h2
                  style="transition-delay: 0.8s"
                  id="btn-title"
                  class="btn-title"
                >Para aplicar lo que sé</h2>
              </transition>
            </div>
          </div>
        </div>
      </div>
    </section>
    <Avance
      class="avance"
      current-page="3"
      total-pages="3"
      prev="3"
    />
  </main>
</template>

<script>
import AppHeader from '@/components/AppHeader'
import Avance from '@/components/Avance'
export default {
  components: {
    AppHeader,
    Avance
  },
  methods: {
    paraSaberBtn() {
      this.$router.push('/5')
    },
    paraHacerBtn() {
      this.$router.push('/6')
    },
    paraAplicarBtn() {
      this.$router.push('/6')
    }
  }
}
</script>

<style lang="scss" scoped>
.slide4 {
  height: 100%;
}
.title {
  background-color: #fff;
  width: 100%;
  min-height: 50px;
  box-shadow: 3px 5px 10px 0 rgba(0, 0, 0, 0.3);
  padding: 10px;
  margin-bottom: 20px;
  text-align: center;
  h1 {
    font-size: 1rem;
    font-weight: 900;
  }
}
.content-inner-wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  margin-bottom: 20px;
}
.content-sec {
  display: flex;
  align-items: center;
  justify-content: space-around;
  width: 100%;
  text-align: center;
  &:nth-child(3) {
    .content-sec-imgBtn {
      order: -1;
    }
  }
  .content-sec-imgBtn {
    order: 2;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    position: relative;
    margin-bottom: 30px;
    width: 100%;
    max-width: 182px;
    .content-sec-img {
    }

    button {
      position: absolute;
      bottom: 0px;
      left: 0;
      img {
        width: 100%;
        height: auto;
        max-width: 182px;
      }
    }
  }
}
.btn-title {
  font-size: 1.2rem;
}
.connect-dots {
  height: 60px;
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 10px auto;
  img {
    transform: rotate(90deg);
    width: 100%;
    height: auto;
    max-width: 60px;
  }
}
@media (min-width: 768px) {
  .container {
    padding-left: 50px;
    padding-top: 70px;
    height: 100%;
    display: flex;
    flex-direction: column;
  }
  .title {
    width: 75%;
    margin-bottom: 40px;
    h1 {
      font-size: 1.3rem;
    }
  }
  .content-inner-wrapper {
    flex-direction: row;
  }
  .content-sec {
    flex-direction: column;

    .content-sec-imgBtn {
      order: 0;
    }
  }
  .btn-title {
    font-size: 1.6rem;
  }
  .connect-dots {
    width: 100%;
    max-width: 90px;
    img {
      transform: rotate(0);
      max-width: 100%;
    }
  }
}
.fade-fly-right-enter-active,
.fade-fly-right-leave-active {
  transition: all 0.7s;
}
.fade-fly-right-enter,
.fade-fly-right-leave-to {
  opacity: 0;
  transform: translateX(150%);
}

.fade-fly-up-enter-active,
.fade-fly-up-leave-active {
  transition: all 0.7s;
}
.fade-fly-up-enter,
.fade-fly-up-leave-to {
  opacity: 0;
  transform: translateY(30%);
}
.fade-fly-down-enter-active,
.fade-fly-down-leave-active {
  transition: all 0.7s;
}
.fade-fly-down-enter,
.fade-fly-down-leave-to {
  opacity: 0;
  transform: translateY(-30%);
}
</style>