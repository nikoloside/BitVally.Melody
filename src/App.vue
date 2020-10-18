<template>
  <div id="app flex-container-spacebetween">
    <div id="wrap">
      <Header></Header>
      <div id="wrap-contents">
        <router-view/>
      </div>
      <Footer></Footer>
    </div>
  </div>
</template>

<script>
import Header from '@/toppage/sections/covid19_header';
import Footer from '@/toppage/sections/covid19_footer';

export default {
  name: 'App',
  components: {
    Header,
    Footer,
  },
};
</script>

<style  lang="scss">
@import "./commons/_variables.scss";
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: $color-black;
}

// 以下是所有的页面共通的scss 共通class
// Google Font
@import url('https://fonts.googleapis.com/css?family=Noto+Sans+JP:400,500,700|Poppins:400,500,700&display=swap&subset=japanese');

// Plate的共通样式
.wrap-shadow {
  box-shadow: $box-shadow-wrap;
  border-radius: 12px;
}

// flex的共通化
.flex-container-start {
  display: flex;
  justify-content: flex-start;
  align-items: center;
}

.flex-container-spacebetween {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.flex-direction-column {
  flex-direction: column;
}

// link的共通样式
ul {
  list-style:none;
}

a {
  text-decoration: none;
  color:$color-black;
  transition: color .3s ease;
  -webkit-transition: color .3s ease;
  &.router-link-exact-active {
    color: $color-black;
  }
}
a:hover{
    color: $color-blue;
}

body {
  margin: 0;
}

// 这里开始是router-page的共通css

#wrap {
  background-color : #fff;
}
#wrap-contents {
  // 先对应 960 和 1280 之间，等增加样式之后统一加@ media 的tag
  // 基本所有的component样式都是能默认自适应的
  min-width: 320px;
  max-width: 1280px;
  margin: 0 auto;
}

//! 以下是covid19_top内部所有的共通css class
// Header大概
.page-container {
  margin-top: 132px;
}
// Covid19_top的标准h1
.section {
  display: flex;
  flex-direction: row;
  margin-left: 24px;
  color: $color-black;
  text-align: left;

  .section-left {
    width: 4px;
    height: 36px;
    border-radius: 2px;
    background: $color-primary;
    border-radius: 2px;
    margin-right: 9px;

    @media (max-width: $breakpoint-sp) {
      height: 30px;
    }
  }

  @include noto-font-001em(24px, bold);
  @media (max-width: $breakpoint-pc) {
    margin-left: 16px;
  }
  @media (max-width: $breakpoint-sp) {
    margin-left: 16px;
    @include noto-font-001em(20px, bold);
  }
}

.section-wrapper {
  margin: 24px;
  padding: 24px;

  @media (max-width: $breakpoint-sp) {
    margin: 24px 16px;
    padding: 24px 16px;
  }
}

.wrap-sp-display{
  display: none;
  @media (max-width: $breakpoint-sp) {
    display: flex;
  }
}

</style>
