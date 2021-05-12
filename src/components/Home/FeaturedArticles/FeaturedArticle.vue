<style lang="scss" scoped>
.title {
  display: flex;
  align-items: center;
  background-color: #282828;
  height: 40px;
  width: 100%;

  h2 {
    font-size: 16px;
    padding-left: 20px;
    color: #fff;
  }
}
.articles-wrapper {
  padding-top: 30px;
  display: grid;
  grid-template-columns: auto;
  @include media(sm) {
    grid-template-columns: auto auto auto;
  }
  @include media(md) {
    grid-template-columns: auto auto auto auto auto;
  }
  .articles-items {
    margin-right: 30px;
    margin-bottom: 20px;
    color: #fff;
  }
}
</style>
<template>
  <section>
    <div class="title">
      <h2>FEATURED ARTICLES</h2>
    </div>
    <div class="articles-wrapper">
      <div class="articles-items" v-for="(item, index) in getData" :key="index">
        <Article :article="item" />
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import { Component, Vue, Prop, Watch } from 'vue-property-decorator';
import Article from './Article.vue';
@Component({
  components: {
    Article,
  },
})
export default class FeaturedArticle extends Vue {
  @Prop({
    required: true,
  })
  readonly data!: any;
  @Watch('data')
  onModelChange(val: any) {
    this.lastMovies = val;
  }

  lastMovies: any = this.data;
  get getData() {
    return this.lastMovies;
  }
  mounted() {
    // if (this.lastMovies) {
    //   this.lastMovies = this.lastMovies.map((item: any) => {
    //     return item.list;
    //   });
    // }
  }
}
</script>
