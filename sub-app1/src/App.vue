<template>
    <div id="app">
        <div id="nav">
            <h1>我是子应用一，sub-app1</h1>
            <router-link to="/sub-app1">子应用一:首页dsds</router-link>
            |||
            <router-link to="/sub-app1/about">子应用一:about页面</router-link>
        </div>

      <div class="test">
      测试数据:
        aaa: {{aaa}}
        <button @click="change_aaa">改变aaa</button>
        <button @click="goToday">goToday</button>
      </div>
        <router-view/>
    </div>
</template>
<script>
    import Vue from 'vue'

    export default {
      data(){
        return{
          aaa:1
        }
      },
        methods: {
            goToday() {
              alert(111)
            },
          change_aaa(){
this.aaa++
          }
        },
        mounted() {
          const  _this= this;
            // 将backToday方法绑定到window下面，提供给外部调用
            console.log(window, 'window app1');

            Vue.prototype['aaaaaaaaaaaaaaa'] = () => {
                this.goToday()
            }
          window.atest =this;
          window.ccccc= function (){
            console.log(Vue,'Vue');
            _this.goToday()
          }
            setTimeout(() => {

                console.log(this, 'this app1');

            }, 5000)

        }
    }
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
