<template>
  <div id="app">
    <div id="nav">
        <h1>我是子应用二，sub-app2</h1>
        <router-link to="/sub-app2">子应用二:首页</router-link> |
        <router-link to="/sub-app2/about">子应用二:about页面</router-link>
    </div>
    <div>jlw:{{jlw}}</div>

    <router-view/>
  </div>
</template>

<script>
export default {
  data() {
    return {
      jlw: 1
    };
  },
  methods: {
    change_jlw() {
      this.jlw++;
    }
  },
  mounted() {
    window.app2_test = this;
  }
};
</script>
<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
