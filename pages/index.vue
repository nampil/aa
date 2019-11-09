<template>
  <main>
    <section
      id="inicioSlide"
      class="inicioSlide"
      ref="focusTarget"
    >
      <div class="container">
        <div class="guia-nav">
          <button
            role="button"
            @click.prevent="showModal"
          >
            Guia de navegación
            <img
              class="btn-icon"
              src="@/assets/images/hand-pointer.svg"
              alt="Mano haciendo click Icono "
            />
          </button>
        </div>
        <div class="main-content">
          <div class="main-content-title">
            <h1>Netiqueta: Comportamiento y buen uso del lenguaje en entornos virtuales.</h1>
          </div>
          <div class="main-content-desc">
            <div class="cd-logo">
              <img
                src="@/assets/images/cd-logo.png"
                alt="Logo de Ciudadania Digital"
                srcset
              />
            </div>
            <div class="main-content-desc-inner">
              <div class="desc">
                <h2>Módulo 1</h2>
                <p>¿Cómo debo comportarme al interactuar en las plataformas digitales?</p>
              </div>
              <div class="desc">
                <h2>Unidad 3</h2>
                <p>Nuevos lenguajes, nuevos problemas de comunicación.</p>
              </div>
            </div>
          </div>
          <button
            role="button"
            aria-label="Empezar Curso"
            class="empezar-btn"
            @click="$router.push('/2')"
          >Empezar</button>
        </div>
      </div>
      <div class="logos">
        <img
          src="@/assets/images/logosa.png"
          alt="Logos de MinTic y Ciudadania Digital"
        />
      </div>
      <div class="people">
        <img
          src="@/assets/images/people.png"
          alt="Dibujo de personas usando dispositivos digitales en el parque"
        />
      </div>
      <div class="overlay"></div>
    </section>
    <transition name="fade">
      <div
        id="guiaNavegacion-modal"
        class="guiaNavegacion-modal"
        role="alertdialog"
        aria-hidden="true"
        v-show="showGuiaNavegacionModal"
      >
        <div class="modal-overlay">
          <div class="video-wrapper">
            <div class="video">
              <iframe
                width="1000"
                height="562"
                src="https://www.youtube.com/embed/E8GoB3O6Svg"
                frameborder="0"
                allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
                allowfullscreen
              ></iframe>
            </div>
            <div class="close-modal">
              <button
                aria-label="Cerrar"
                class="close-btn"
                @click="closeModal"
              >X</button>
            </div>
          </div>
        </div>
      </div>
    </transition>
  </main>
</template>

<script>
export default {
  data() {
    return {
      showGuiaNavegacionModal: false
    }
  },
  methods: {
    showModal() {
      document.getElementById('inicioSlide').setAttribute('aria-hidden', 'true')
      document
        .getElementById('guiaNavegacion-modal')
        .setAttribute('aria-hidden', 'false')
      this.showGuiaNavegacionModal = true
    },
    closeModal() {
      document
        .getElementById('inicioSlide')
        .setAttribute('aria-hidden', 'false')
      document
        .getElementById('guiaNavegacion-modal')
        .setAttribute('aria-hidden', 'true')
      this.showGuiaNavegacionModal = false
    }
  },
  mounted() {}
}
</script>

<style scoped lang="scss">
.inicioSlide {
  height: 100%;
}

.overlay {
  position: absolute;
  background-color: rgba(6, 141, 204, 0.2);
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 0;
  padding: $mainSectionPadding;
}

.guia-nav {
  width: 100%;
  position: relative;
  z-index: 3;
  margin-bottom: 20px;
  button {
    margin-top: 10px;
    width: 100%;
    padding: 8px 8px;
    font-family: 'Nunito', sans-serif;
    font-size: 15px;
    border: none;
    background-color: $purple_light;
    color: #fff;
    cursor: pointer;
    border-radius: 4px;
    box-shadow: 0 3px 1px 0 lighten($color: $purple_light, $amount: 20%);
    display: flex;
    justify-content: center;
    align-items: center;
  }
}
.btn-icon {
  width: 20px;
  margin-left: 7px;
}
.main-content {
  background-color: #fff;
  box-shadow: 4px 4px 0 0 $dark;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.main-content-title {
  color: #fff;
  background: $dark;
  padding: 8px 25px;
  h1 {
    font-size: 1.3rem;
    font-weight: 600;
  }
}
.cd-logo {
  width: 50%;
  margin: 10px auto;
  padding: $mainSectionPadding * 1.3;
  display: flex;
  justify-content: center;
  align-items: center;
  align-self: flex-start;
  img {
    width: 100%;
    height: auto;
  }
}
.main-content-desc-inner {
  padding: 0 15px;
  .desc {
    margin-bottom: 20px;
  }
}
.empezar-btn {
  width: 80%;
  margin: 0 auto 20px;
  padding: 4px 8px;
  font-family: 'Nunito', sans-serif;
  font-size: 1.5rem;
  border: none;
  background-color: $purple_light;
  color: #fff;
  border-radius: 4px;
  box-shadow: 0 5px 2px 0 lighten($color: $purple_light, $amount: 20%);
  cursor: pointer;
}

.logos {
  position: relative;
  z-index: 3;
  text-align: center;
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 100%;
  padding-bottom: 10px;
  padding-top: 10px;
  background: #fff;

  img {
    width: 50%;
    align-self: center;
    height: auto;
  }
}

.people {
  display: none;
}

.guiaNavegacion-modal {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 6;
  .modal-overlay {
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: rgba(0, 0, 0, 0.7);
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .video-wrapper {
    padding: $mainSectionPadding * 2;
    width: 100%;
    max-width: 600px;
    position: relative;
  }
  .close-btn {
    width: 30px;
    height: 30px;
    position: absolute;
    top: 5px;
    right: 5px;
    background-color: $purple;
    border-radius: 50%;
    color: #fff;
    font-weight: bold;
    font-size: 1.3rem;
    cursor: pointer;
  }
  .video {
    position: relative;
    padding-bottom: 56.25%; /* 16:9 */
    padding-top: 25px;
    height: 0;
    width: 100%;

    iframe {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
    }
  }
}

@media (min-width: 768px) {
  .container {
    padding: 15px;
    flex-direction: row;
    height: 70%;
  }

  .guia-nav {
    width: 31%;
    button {
      margin-top: 40px;
      width: 95%;
    }
  }
  .main-content-desc {
    display: flex;
    flex-grow: 2;
    padding-top: 20px;
    padding-bottom: 50px;
  }
  .cd-logo {
    width: 30%;
  }

  .empezar-btn {
    width: 30%;
    margin: 0;
    min-width: 150px;
    padding: 6px 8px;
    font-family: 'Nunito', sans-serif;
    font-size: 30px;
    border: none;
    background-color: $purple_light;
    color: #fff;
    position: absolute;
    right: 20px;
    bottom: -20px;
    border-radius: 4px;
    box-shadow: 0 5px 2px 0 lighten($color: $purple_light, $amount: 20%);
    cursor: pointer;
  }
  .people {
    display: block;
    display: block;
    position: absolute;
    bottom: -50px;
    left: 0;
    width: 90%;
    z-index: 2;
    pointer-events: none;
    img {
      width: 100%;
    }
  }
  .logos {
    overflow: hidden;
    margin-top: 100px;
    max-height: 100px;
    img {
      width: 40%;
      max-height: 100%;
    }
  }
}

@media (min-width: 992px) {
  .container {
  }
  .overlay {
  }
  .guia-nav {
    button {
    }
  }
  .cd-logo {
    width: 50%;
  }
  .main-content {
    display: flex;
    flex-direction: column;
    position: relative;
  }
  .main-content-title {
    width: 100%;
  }

  .main-content-desc {
    justify-content: center;
    align-items: center;
    flex-direction: row;
  }
  .main-content-desc-title {
  }

  .main-content-desc-inner {
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding-right: $mainSectionPadding * 5;
    .desc {
      margin-bottom: $mainSectionPadding * 2;
      margin-left: $mainSectionPadding * 9;
      font-weight: 900;
      font-size: 1.5rem;
      h2 {
        font-size: 2rem;
        font-weight: bold;
      }
    }
  }

  .empezar-btn {
    width: 30%;
    margin: 0;
    min-width: 150px;
    padding: 6px 8px;
    font-family: 'Nunito', sans-serif;
    font-size: 30px;
    border: none;
    background-color: $purple_light;
    color: #fff;
    position: absolute;
    right: 20px;
    bottom: -20px;
    border-radius: 4px;
    box-shadow: 0 5px 2px 0 lighten($color: $purple_light, $amount: 20%);
    cursor: pointer;
  }
  .logos {
    position: absolute;
    z-index: 3;
    flex-grow: 2;
    bottom: 0;
    top: 82%;
    left: 0;
    right: 0;
    overflow: hidden;
    margin-top: 0;
    img {
      width: unset;
      height: 80%;
      max-height: 100%;
    }
  }
  .people {
    display: block;
    position: absolute;
    bottom: -50px;
    left: 0;
    width: 100%;
    z-index: 2;
    pointer-events: none;
    img {
      width: 100%;
    }
  }
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
</style>
