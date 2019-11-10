<template>
  <main>
    <AppHeader breadcrumb="Unidad 3: Nuevos lenguajes, nuevos problemas de comunicación" />
    <section class="slide5">
      <div class="container">
        <div class="content">
          <div class="content-inner-wrapper">
            <div class="content-title">
              <div class="rec">
                <h1>Para Saber</h1>
                <div class="content-title-logo">
                  <img
                    src="@/assets/images/para-saber-logo.png"
                    alt
                  />
                </div>
              </div>
            </div>
            <div class="content-img">
              <img
                src="@/assets/images/niña-parque.png"
                alt
              />
            </div>
          </div>
        </div>
      </div>
    </section>
    <Avance
      class="avance"
      next="6"
      currentPage="1"
      totalPages="28"
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
.slide5 {
  height: 100%;
  overflow: hidden;
  min-height: 80vh;
}

.content-inner-wrapper {
  display: flex;
  flex-wrap: wrap;
  height: 100%;
  margin-bottom: 45px;
  align-items: center;

  padding-top: 40px;
}
.content {
  height: 100%;
}

h1 {
  color: #fff;
  padding: 20px 0 20px 70px;
  &::before {
    content: '';
    display: block;
    position: absolute;
    left: 10px;
    top: 50%;
    transform: translateY(-50%);
    width: 100%;
    height: 30px;
    max-width: 50px;
    background-image: url('../assets/images/title-dots.svg');
    background-size: contain;
    background-repeat: no-repeat;
    background-position: center;
  }
}
.content-title {
  position: relative;
  display: flex;
  width: 90%;
  margin-bottom: 20px;
}
.rec {
  background-color: #7a48fe;
  display: flex;
  width: 100%;
  max-width: 400px;
  height: 100px;
  align-items: center;
  position: relative;
}
.content-title-logo {
  display: flex;
  align-items: center;
  justify-content: center;
  position: absolute;
  right: 0;
  top: 50%;
  width: 50%;
  transform: translateX(50%) translateY(-50%);
  img {
    max-width: 150px;
  }
}

img {
  width: 100%;
  height: auto;
}

@media (min-width: 768px) {
  .slide5 {
    display: flex;
    align-items: center;
  }
  .container {
    height: 100%;
  }
  .content-inner-wrapper {
    flex-wrap: nowrap;
    align-items: center;
    height: 100%;
  }
  .content-title {
    width: 100%;
  }
  .content-title-logo {
    img {
      max-width: 220px;
    }
  }
}
</style>