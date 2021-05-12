<style lang="scss" scoped>
.menu-wrapper {
  display: flex;
  align-items: center;

  li {
    display: flex;
    align-items: center;
    background-color: #292929;
    border-right: 1px solid #090909;
    a {
      color: #fff;
      padding: 20px 10px;
      &.router-link-active {
        display: flex;
        align-items: center;
        color: #e41f43;
        background-color: #333333;
        border-left: 1px solid #090909;
      }
    }
  }
}
</style>
<template>
  <nav>
    <ul class="menu-wrapper">
      <li v-for="(item, index) in navItems" :key="index">
        <router-link :to="item.to" exact>{{ item.name }}</router-link>
      </li>
    </ul>
  </nav>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
@Component({})
export default class Menu extends Vue {
  navItems = [
    {
      name: 'HOME',
      to: '/',
    },
    {
      name: 'CELEBRITIES',
      to: '/celebrities',
    },
    {
      name: 'GALLARY',
      to: '/gallary',
    },
    {
      name: 'NEWS',
      to: '/news',
    },
    {
      name: 'CONTACTS',
      to: '/contacts',
    },
  ];
}
</script>
