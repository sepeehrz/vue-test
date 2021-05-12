<style lang="scss" scoped>
.search-wrapper {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 60px;
  padding: 0 20px;
  .login {
    a {
      color: #fff;
      font-size: 14px;
    }
    a:first-child {
      margin-right: 20px;
    }
  }
  .search {
    position: relative;
    .search-box {
      background-color: #222222;
      border: none;
      width: 300px;
      height: 25px;
    }
    .search-svg {
      position: absolute;
      right: 3px;
      top: 3px;
      svg {
        fill: #e41f43;
      }
    }
  }
}
.nav-wrapper {
  @extend .search-wrapper;
  background-color: #2b2b2b;
  .logo {
    display: flex;
    .text {
      font-size: 30px;
      font-weight: bold;
      color: #fff;
    }
    .red-zone {
      padding-left: 5px;
      padding-top: 5px;
      span {
        background-color: #e41f43;
        padding: 0 3px;
        color: #212121;
        font-size: 14px;
        font-weight: bold;
      }
    }
  }
}
</style>

<template>
  <section>
    <div class="search-wrapper">
      <div class="login">
        <a href="#">Login</a>
        <a href="#">Entries</a>
      </div>
      <div class="search">
        <input type="text" class="search-box" />
        <div class="search-svg">
          <svg
            fill="#000000"
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 48 48"
            width="18px"
            height="18px"
          >
            <path
              d="M 20.5 6 C 12.515556 6 6 12.515562 6 20.5 C 6 28.484438 12.515556 35 20.5 35 C 23.773158 35 26.788919 33.893018 29.220703 32.050781 L 38.585938 41.414062 A 2.0002 2.0002 0 1 0 41.414062 38.585938 L 32.050781 29.220703 C 33.893017 26.788918 35 23.773156 35 20.5 C 35 12.515562 28.484444 6 20.5 6 z M 20.5 10 C 26.322685 10 31 14.677319 31 20.5 C 31 23.295711 29.914065 25.820601 28.148438 27.697266 A 2.0002 2.0002 0 0 0 27.701172 28.144531 C 25.824103 29.912403 23.29771 31 20.5 31 C 14.677315 31 10 26.322681 10 20.5 C 10 14.677319 14.677315 10 20.5 10 z"
            />
          </svg>
        </div>
      </div>
    </div>
    <div class="nav-wrapper">
      <div class="logo">
        <span class="text">CELEBRITIES</span>
        <div class="red-zone">
          <span>FAN ZONE</span>
        </div>
      </div>
      <div class="nav">
        <Menu />
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Menu from './Menu.vue';
@Component({
  components: {
    Menu,
  },
})
export default class Header extends Vue {}
</script>
