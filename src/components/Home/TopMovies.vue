<style lang="scss" scoped>
.box-image {
  width: 100%;
  height: 100%;
  position: relative;
  background-size: 100% 100%;
  background-repeat: no-repeat;
  img {
    width: 100%;
    height: 100%;
  }
  .movie-description {
    position: absolute;
    bottom: 30px;
    left: 0;
    right: 0;
    text-align: center;

    .movie-name {
      color: #fff;
      font-size: 40px;
    }
    .movie-text {
      font-size: 20px;
      color: #e41f43;
    }
  }
}
</style>
<template>
  <div
    class="box-image"
    :style="{
      'background-image':
        'linear-gradient' +
        '(' +
        'rgba(0, 0, 0, 0.5)' +
        ',' +
        'rgba(0, 0, 0, 0.5)' +
        ')' +
        ',' +
        'url(' +
        dataBanner.ThumbImage +
        ')',
    }"
  >
    <div class="movie-description">
      <slot name="description">
        <h2 class="movie-name">{{ dataBanner.Title }}</h2>
        <div class="movie-text">OCAECAT CUPIDATAT NON PROIDE</div>
      </slot>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop, Watch } from 'vue-property-decorator';
@Component({})
export default class TopMovie extends Vue {
  @Prop({
    // type: Object,
    required: true,
  })
  readonly data!: any;
  @Watch('data')
  onModelChange(val: any) {
    this.dataBanner = val;
  }

  dataBanner: any = this.data;
}
</script>
