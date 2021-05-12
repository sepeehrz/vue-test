<style lang="scss" scoped>
.not-found {
  height: 100vh;
  color: #fff;
  text-align: center;
  padding-top: 50px;
  p {
    margin-top: 20px;
    a {
      color: red;
      padding-left: 5px;
      text-decoration: underline;
    }
  }
}
</style>
<template>
  <section class="not-found">
    <h1>(404) Page NotFound</h1>
    <p>return <a href="/">HOME</a></p>
  </section>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
@Component({})
export default class NotFound extends Vue {}
</script>
