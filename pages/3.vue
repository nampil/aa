<template>
  <main>
    <AppHeader breadcrumb="Contenidos de la unidad" />
    <section>
      <div class="container">
        <div class="wrapper">
          <transition
            appear
            name="fade"
          >
            <Block
              heading="true"
              text="¿Nuevos Lenguajes?"
            ></Block>
          </transition>

          <div class="blocks">
            <transition
              appear
              name="fade2"
            >
              <div class="block-group">
                <Block text="¿Cuales son los nuevos problemas de comunicación?"></Block>

                <Block
                  class="sub-block"
                  text="Situaciones que se presentan a raíz de los nuevos problemas de comunicación"
                ></Block>
              </div>
            </transition>
            <transition
              appear
              name="fade3"
            >
              <div class="block-group">
                <Block text="¿Cuales son los términos que se popularizan a través de Internet?"></Block>
                <Block
                  class="sub-block"
                  text="Uso de los emoticones y siglas en inglés"
                ></Block>
              </div>
            </transition>
            <transition
              appear
              name="fade4"
            >
              <div class="block-group">
                <Block
                  text="¿Cómo son los nuevos lenguajes, diálogos para foros y comunidades virtuales?"
                ></Block>
                <Block
                  class="sub-block"
                  text="Reglas de escritura en internet"
                ></Block>
              </div>
            </transition>
          </div>
        </div>
      </div>
    </section>
    <Avance
      class="avance"
      next="4"
      current-page="2"
      total-pages="3"
      prev="2"
    />
  </main>
</template>

<script>
import AppHeader from '@/components/AppHeader'
import Block from '@/components/Block'
import Avance from '@/components/Avance'
export default {
  name: 'Slide3',
  components: { AppHeader, Block, Avance },
  data() {
    return {}
  }
}
</script>

<style lang="scss" scoped>
.wrapper {
  display: flex;
  flex-direction: column;
  margin-bottom: 30px;
  width: 100%;
}

.block-group {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.block {
  font-size: 1em;
  &.heading {
    font-size: 1.3em;
  }
}
.sub-block {
  margin-bottom: 20px;
  border-color: $purple;
  width: 80%;
  font-size: 0.8em;
  &::before,
  &::after {
    background-color: $purple;
  }
}
@media (min-width: 768px) {
  .container {
    padding-top: 70px;
  }
  .blocks {
    display: flex;
  }
  .block {
    font-size: 0.6em;
    height: 130px;
    line-height: 1.7em;
    display: flex;
    align-items: center;

    &.heading {
      display: inline-block;
      align-self: center;
      font-size: 1em;
      margin-bottom: 30px;
      display: flex;
      align-items: center;
      justify-content: center;
      height: unset;
      padding: 8px 30px;
    }
  }
  .block-group {
    width: 33%;
    justify-content: start;
    align-items: center;
    margin-bottom: 20px;
  }
}

@media (min-width: 768px) {
  .block {
    font-size: 0.8em;
    &.heading {
      font-size: 1.1em;
    }
  }
}

.fade-enter-active,
.fade-leave-active {
  transition: all 0.7s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
  transform: translateY(150%);
}

.fade2-enter-active,
.fade2-leave-active {
  transition: all 0.7s 0.3s;
}
.fade2-enter,
.fade2-leave-to {
  opacity: 0;
  transform: translateY(150%);
}

.fade3-enter-active,
.fade3-leave-active {
  transition: all 0.7s 0.6s;
}
.fade3-enter,
.fade3-leave-to {
  opacity: 0;
  transform: translateY(150%);
}

.fade4-enter-active,
.fade4-leave-active {
  transition: all 0.7s 0.9s;
}
.fade4-enter,
.fade4-leave-to {
  opacity: 0;
  transform: translateY(150%);
}
</style>