<style lang="scss" scoped>
.article {
  .image {
    img {
      max-width: 100%;
      max-height: 100%;
    }
  }
  .article-description {
    color: #fff;
    text-align: center;
    .article-name {
      color: #7c8181;
      line-height: 1.6;
    }
    .article-text {
      color: #fff;
      line-height: 1.4;
      @include media(md) {
        margin: 0 auto;
        max-width: 200px;
      }
    }
  }
}
</style>
<template>
  <div class="article">
    <div class="image">
      <img :src="articleItem.PortraitImage" :alt="``" />
    </div>
    <div class="article-description">
      <div class="article-name">{{ articleItem.Title }}</div>
      <div class="article-text">OCAECAT CUPIDATAT NON PROIDE</div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop, Watch } from 'vue-property-decorator';
@Component({})
export default class Article extends Vue {
  @Prop({
    type: Object,
    required: true,
  })
  readonly article!: Object;

  @Watch('article')
  onModelChange(val: any) {
    this.articleItem = val;
  }
  articleItem = this.article;
}
</script>
