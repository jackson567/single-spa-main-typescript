<template>
  <div id="root"  class="main">
    <div id="nav">
      <nav>
        <ol>
          <li>
            <a @click="goto('vue sub-app1','/sub-app1')">子应用一</a>
          </li>
          <li>
            <a @click="goto('vue sub-app2','/sub-app2')">子应用二</a>
          </li>
        </ol>
      </nav>
    </div>
    <div class="control-module">
      <div>这里是 micro demo,绝对定位</div>
      <button @click="change_aaa">控制app1,改变aaa</button>
      <br>
      <br>
      <div>about 頁面改變</div>
      <button @click="change_jlw">控制app1,改变  jlw</button>
      |<br>
      <br>
      <div>app 頁面改變</div>
      <button @click="change_app2">控制app2,改变  app2</button>
   
       </div>

    <!--<div v-if="loading">loading</div>-->
    <div id="router-view" class="router-view" v-html="content">

    </div>
  </div>
</template>

<script>
import Vue from "vue";
export default {
  name: "framework",
  props: {
    // loading: Boolean,
    content: String
  },
  methods: {
    // goto(title, href) {
    //   this.$router.push(href)
    // },
    goto(title, href) {
      console.log("title", title, "href", href);
      window.history.pushState({}, title, href);
    },
    change_aaa() {
      window.atest.change_aaa();
    },
    change_jlw() {
      window.abouttest.change_jlw();
    },
    change_app2() {
      window.app2_test.change_jlw();
    },
  },
  mounted() {
    console.log(this, "this  demo");
    let v = new Vue();

    console.log(v, "v");

    console.log(window, "window  demo");
  },
  beforeUpdate() {
  },
  updated() {
  },
  beforeDestroy() {}
};
</script>

<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    cursor: pointer;
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
.main{
      position: relative;
    .control-module{
        position: absolute;
        left:60vw;
        top:20vh;
    }
}

</style>
