<template>
  <div class="page-container">
    <PickUp></PickUp>

    <div id="section-news" class="section section-news">
      <div class="section-left" />{{ $t("messages.titlenews") }}
    </div>
    <News></News>
    <div class="section-readmore">
      <router-link class="newsReadmore" to="/news" v-scroll-to="'#covid19-article'">
        {{ $t("messages.newsreadmore") }}
      </router-link>
    </div>

  </div>
</template>

<script>
import PickUp from '@/toppage/sections/covid19_pickup';
import News from '@/toppage/sections/covid19_news';

export default {
  name: 'TopPage',
  components: {
    PickUp,
    News,
  },
  data() {
    return {
      msg: 'Welcome to Your Vue.js App',
    };
  },
  head: {
    title() {
      return {
        inner: this.$i18n.t('messages.metatitle'),
        separator: '|',
        complement: 'Top',
      };
    },
    meta() {
      return [
        { name: 'description', content: this.$i18n.t('messages.metadescription') },
        { name: 'viewport', content: 'width=device-width,initial-scale=1.0,user-scalable=no' },
        { charset: 'utf-8' },
        { property: 'og:type', content: 'website' },
        { property: 'og:title', content: '「さよならコロナ」感染情報チェックマップ' },
        { property: 'og:url', content: 'https://survival-jp.com' },
        { property: 'og:image', content: 'https://res.cloudinary.com/df6wesepg/image/upload/v1588696192/promotion/OGP_jp_mehcze.png' },
        { property: 'og:description', content: '「さよならコロナ」1分で新型コロナウイルスのリアルタイム情報をまとめて感染事例チェックマップ #感染事例チェックマップ #さよならコロナ #covid19 #新型肺炎 #新型コロナウイルス対策まとめ' },
        { property: 'twitter:card', content: 'summary_large_image' },
      ];
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style  lang="scss">
@import "@/commons/_variables.scss";

// ver1.2仕様 必须通过列表进行切换
.section-dashboard {
  display: flex;
  @media (max-width: $breakpoint-pc) {
    flex-direction: column;
  }
}
.section-japan {
  display: flex;
  flex-direction: column;
  width: 50%;
  @media (max-width: $breakpoint-pc) {
    width:100%;
  }
}
.section-infect {
  .section {
    margin-left: 0px;
  }
  margin: 12px 24px;
  @media (max-width: $breakpoint-pc) {
    margin: 12px 16px;
  }
}
.section-region {
  .section {
    margin-left: 0px;
  }
  margin: 12px 24px;
  @media (max-width: $breakpoint-pc) {
    margin: 12px 16px;
  }
}
.section-news {
  width: 100%;
}
.additional-topinfo {
  @include noto-font-001em(14px, bold);
  padding: 0;
  margin: 8px 0;
  color: $color-gray;
  position: absolute;
  top: -48px;
  right: 0px;

  &:last-child {
    margin-bottom: 0;
  }

  @media (max-width: $breakpoint-sp) {
    @include noto-font-001em(10px, normal);
    margin: 4px 0;
  }
}

.additional-info {
  @include noto-font-001em(14px, normal);
  padding: 0;
  margin: 8px 0;
  color: $color-lightgray;

  &:last-child {
    margin-bottom: 0;
  }

  @media (max-width: $breakpoint-sp) {
    @include noto-font-001em(10px, normal);
    margin: 4px 0;
  }
}

.section-readmore {
  display: flex;
  width: 100%;
  justify-content: center;
  align-items: center;

  .newsReadmore {
    width: 115px;
    height: 42px;
    margin-bottom: 48px;
    padding: 18px 0;

    display: flex;
    justify-content: center;
    align-items: center;
    @include noto-font-001em(14px, bold);
    line-height: 200%;
    color: $color-gray;

    border: 2px solid $color-gray;
    box-sizing: border-box;
    border-radius: 22px;
    transition: color 0.3 ease;
    transition: all 0.3 ease;
    &:hover {
        color: $color-lightgray;
        border: 2px solid $color-lightgray;
    }
  }
}
</style>
