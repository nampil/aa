<template>
  <nav>
    <ul>
      <li class="home-link-li">
        <a href="/">
          <img
            src="@/assets/images/home-w.svg"
            alt="Inicio"
          />
        </a>
      </li>
      <li
        v-if="advanced"
        class="menu-link-li"
      >
        <a href="/4">
          <img
            src="@/assets/images/dots-p.svg"
            alt="Menu"
          />
        </a>
      </li>
    </ul>
    <div class="breadcrumb">{{breadcrumb}}</div>
    <div class="sub-breadcrumb">{{subBreadcrumb}}</div>
  </nav>
</template>

<script>
export default {
  name: 'AppHeader',
  props: ['breadcrumb', 'subBreadcrumb'],
  computed: {
    advanced() {
      let number = Number(this.$route.fullPath.substring(1))

      return number >= 5
    }
  }
}
</script>

<style scoped lang="scss">
nav {
  position: relative;
  display: flex;
  align-items: center;
  padding-left: 15px;
  height: 45px;
  line-height: 45px;
  background-color: $purple;
  border-top-right-radius: $headerBorderRadius;
  z-index: 999;
  ul {
    list-style: none;
    display: flex;
  }
  li {
    margin: 0 10px 0 0;
    padding: 0 5px;
    display: flex;
    justify-content: center;
    align-items: center;
    &.home-link-li {
      background-color: $purple;
      border-top-right-radius: $headerBorderRadius;
      a {
        display: flex;
        justify-content: center;
        align-items: center;
        img {
          width: 100%;
          max-width: 30px;
          height: auto;
        }
      }
    }

    &.menu-link-li {
      cursor: pointer;
      a {
        img {
          width: 100%;
          max-width: 30px;
          height: auto;
        }
      }
    }
  }
  a {
    text-decoration: none;
    color: #333;
  }
  .breadcrumb {
    padding: 0 50px 0 10px;
    background-color: $turquesa;
    border-top-right-radius: $headerBorderRadius;
    font-size: 0.8rem;
    color: #fff;
  }
}

@media (min-width: 768px) {
  nav {
    position: absolute;
    left: 0;
    top: 10px;
    padding-left: 15px;
    border-top-right-radius: $headerBorderRadius;
    ul {
      list-style: none;
      display: flex;
    }
    li {
      margin: 0 10px 0 0;
      padding: 0 5px;
      display: flex;
      justify-content: center;
      align-items: center;
      &.home-link-li {
        background-color: $purple;
        border-top-right-radius: $headerBorderRadius;

        a {
          display: flex;
          justify-content: center;
          align-items: center;
          img {
            width: 100%;
            max-width: 30px;
            height: auto;
          }
        }
      }

      &.menu-link-li {
      }
    }
    a {
      text-decoration: none;
      color: #333;
    }
    .breadcrumb {
      padding: 0 100px 0 20px;
      font-size: 1rem;
    }
  }
}
</style>