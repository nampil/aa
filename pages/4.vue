<template>
  <main>
    <AppHeader breadcrumb="Mapa de aprendizaje" />
    <section class="slide4">
      <div class="container">
        <h1 class="title">Para crecer como ciudadano digital</h1>
        <div class="content">
          <div class="content-inner-wrapper">
            <div class="content-sec">
              <div class="content-sec-imgBtn">
                <div class="content-sec-img">
                  <img
                    src="@/assets/images/persona-saber.png"
                    alt="Dibujo de Persona con muletas"
                  />
                </div>
                <button aria-labelledby="btn-title">
                  <img
                    src="@/assets/images/para-saber-btn.png"
                    alt="Grafico de una computadora"
                  />
                </button>
              </div>

              <h2
                id="btn-title"
                class="btn-title"
              >Para Saber</h2>
            </div>
            <div class="content-sec connect-dots"></div>
            <div class="content-sec">
              <div class="content-sec-imgBtn">
                <div class="content-sec-img">
                  <img
                    src="@/assets/images/persona-saber.png"
                    alt="Dibujo de Persona con muletas"
                  />
                </div>
                <button aria-labelledby="btn-title">
                  <img
                    src="@/assets/images/para-saber-btn.png"
                    alt="Grafico de una computadora"
                  />
                </button>
              </div>

              <h2
                id="btn-title"
                class="btn-title"
              >Para Saber</h2>
            </div>
            <div class="content-sec connect-dots"></div>
            <div class="content-sec">
              <div class="content-sec-imgBtn">
                <div class="content-sec-img">
                  <img
                    src="@/assets/images/persona-saber.png"
                    alt="Dibujo de Persona con muletas"
                  />
                </div>
                <button aria-labelledby="btn-title">
                  <img
                    src="@/assets/images/para-saber-btn.png"
                    alt="Grafico de una computadora"
                  />
                </button>
              </div>

              <h2
                id="btn-title"
                class="btn-title"
              >Para Saber</h2>
            </div>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
import AppHeader from '@/components/AppHeader'
export default {
  components: {
    AppHeader
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
  flex-direction: column;
}
.content-sec {
  display: flex;
  align-items: center;
  justify-content: space-around;
  width: 100%;
  text-align: center;
  .content-sec-imgBtn {
    order: 2;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    position: relative;
    button {
      position: absolute;
      bottom: 0px;
      img {
        width: 100%;
        height: auto;
        max-width: 182px;
      }
    }
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
    margin-top: 20px;
    h1 {
      font-size: 1.3rem;
    }
  }
  .content-inner-wrapper {
    flex-direction: row;
  }
  .content-sec {
    flex-direction: column;
    &.connect-dots {
    }
    .content-sec-imgBtn {
      order: 0;
    }
  }
}
</style>