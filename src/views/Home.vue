<style lang="scss" scoped>
header {
  display: none;
  @include media(md) {
    display: block;
  }
}
.content-wrapper {
  padding: 30px 20px;
  @include media(md) {
    display: flex;
    justify-content: space-between;
  }
  .articles-wrapper {
    @include media(md) {
      width: calc(100% - 200px);
    }
    .top-banner {
      height: 100vh;
      ::v-deep {
        .movie-name {
          font-size: 60px;
        }
      }
    }
    .selected-movies-wrapper {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      padding: 20px 0;
      .selected-item {
        width: 49%;
        height: 300px;
        margin-bottom: 15px;
      }
    }
  }
  .side-menu {
    width: 170px;
    display: none;
    @include media(md) {
      display: block;
    }
  }
}
</style>
<template>
  <div>
    <header>
      <Header />
    </header>
    <section class="content-wrapper">
      <aside class="side-menu">
        <SideMenu />
      </aside>
      <div class="articles-wrapper">
        <section>
          <div class="top-banner">
            <TopMovie :data="BannerMovie[0]" />
          </div>
          <div class="selected-movies-wrapper">
            <div
              class="selected-item"
              v-for="(item, index) in selectedMovies[0]"
              :key="index"
            >
              <TopMovie :data="item" />
            </div>
          </div>
        </section>
        <section class="">
          <FeaturedArticle :data="lastMovies[0]" />
        </section>
      </div>
    </section>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Header from '@/components/Home/Header/Header.vue';
import SideMenu from '@/components/Home/SideMenu.vue';
import FeaturedArticle from '@/components/Home/FeaturedArticles/FeaturedArticle.vue';
import TopMovie from '@/components/Home/TopMovies.vue';
@Component({
  components: {
    Header,
    SideMenu,
    FeaturedArticle,
    TopMovie,
  },
})
export default class Home extends Vue {
  BannerMovie = [{}];
  selectedMovies = [{}];
  lastMovies = [{}];
  async created() {
    let { data } = await this.axios.get(
      'http://apitest.tek-nic.com/movie/FirstPage'
    );
    let result = data.result;
    let bannerImage = this.filterData(result, 0);
    this.BannerMovie = bannerImage.map((data: any) => {
      for (let item of data.list) {
        return item;
      }
    });

    let filteredSelectedMovies = this.filterData(result, 1);
    this.selectedMovies = filteredSelectedMovies.map((item: any) => {
      return item.list;
    });

    let filteredLastMovie = this.filterData(result, 2);
    this.lastMovies = filteredLastMovie.map((item: any) => {
      return item.list;
    });
  }

  filterData(data: [], value: number) {
    return data.filter((item: any) => item.type == value);
  }
}
</script>
