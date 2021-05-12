<style lang="scss" scoped>
.side-menu-wrapper {
  background-color: #232323;
  width: 100%;
  .side-menu-item {
    padding: 20px 15px;
    a {
      color: #fff;
    }
  }
  &:not(:last-child) {
    border-bottom: 2px solid #292929;
  }
}
</style>
<template>
  <div>
    <ul
      class="side-menu-wrapper"
      v-for="(item, index) in menuItems"
      :key="index"
    >
      <li class="side-menu-item">
        <router-link :to="item.to"> {{ item.name }}</router-link>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
@Component({})
export default class SideMenu extends Vue {
  menuItems = [
    { name: 'ACTORS', to: '#' },
    { name: 'ACTRESSES', to: '#' },
    { name: 'AUTHORS', to: '#' },
    { name: 'DIRECTORS', to: '#' },
    { name: 'HAITI', to: '#' },
    { name: 'HAITI', to: '#' },
    { name: 'HAITI', to: '#' },
    { name: 'HAITI', to: '#' },
    { name: 'HAITI', to: '#' },
    { name: 'HAITI', to: '#' },
    { name: 'HAITI', to: '#' },
    { name: 'HAITI', to: '#' },
    { name: 'HAITI', to: '#' },
    { name: 'HAITI', to: '#' },
    { name: 'HAITI', to: '#' },
    { name: 'HAITI', to: '#' },
  ];
}
</script>
