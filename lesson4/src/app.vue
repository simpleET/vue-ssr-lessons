<template>
  <div id="app">
    <header class="header">
      <p class="title">vue ssr 课程</p>
    </header>
    <transition-group name="fade" mode="out-in">
      <div class="view" key="div">
        <div class="item vue-sell">
          <img src="~/public/vue-sell-visit.png" width="130" alt="">
          <p>
            <a target="_blank" href="https://neveryu.github.io/sell/index.html">用vue构建的外卖app</a>
            <br>
            <span>手机扫码体验效果更佳</span>
          </p>
        </div>
        <div class="item vue-music">
          <img src="~/public/vue-music-visit.png" width="130" alt="">
          <p>
            <a target="_blank" href="https://git.io/fhnor">用vue构建的音乐app</a>
            <br>
              <span>手机扫码体验效果更佳</span>
          </p>
        </div>
        <div class="item vue-tour">
          <img src="~/public/vue-prerender.png" width="130" alt="">
          <p><a target="_blank" href="https://git.io/fp8xw">vue预渲染实例</a></p>
        </div>
      </div>
      <p key="p">
        如基本示例所示，我们为每个请求创建一个新的根 Vue 实例。这与每个用户在自己的浏览器中使用新应用程序的实例类似。如果我们在多个请求之间使用一个共享的实例，很容易导致交叉请求状态污染 (cross-request state pollution)。

        因此，我们不应该直接创建一个应用程序实例，而是应该暴露一个可以重复执行的工厂函数，为每个请求创建新的应用程序实例（app.js）
      </p>
    </transition-group>
    <my-footer></my-footer>
  </div>
</template>
<script>
import MyFooter from './components/footer.vue'
export default {
  components: {
    MyFooter
  },
  created() {
    console.log(111)
  }
}
</script>
<style lang="stylus">
*
  margin 0
  padding 0
body
  font-family -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell, "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
  font-size 15px
  background-color lighten(#eceef1, 30%)
  margin 0
  color #34495e
  overflow-y scroll
div
  box-sizing border-box
</style>

<style scoped lang="stylus">
#app
  position relative
  top 0
  left 0
  width 100%
  min-height 100vh
  padding-bottom 320px
.header
  width 100%
  height 60px
  border-bottom 1px solid #ccc
  background-color #f69
  text-align center
  .title
    line-height 3
    font-size 20px
  a
    display inline-block
    height 60px
    color rgba(255, 255, 255, .8)
    line-height 60px
    transition color .15s ease
    display inline-block
    vertical-align middle
    font-weight 300
    letter-spacing .075em
    margin-right 1.8em
    font-size 18px
    &:hover
      color #fff
    &.router-link-active
      color #fff
      font-weight 400
    
.fade-enter-active, .fade-leave-active
  transition all .2s ease
.fade-enter, .fade-leave-active
  opacity 0
.view
  display flex
  padding 20px 50px
  .item
    flex 1
    a
      color #f36
</style>