<template xmlns:v-bind="http://www.w3.org/1999/xhtml">
  <div id="app">
    <img src="./assets/logo.png">

    <table>
      <tr>
        <th colspan="3">父组件数据</th>
      </tr>
      <tr>
        <td>name</td>
        <td>{{ name }}</td>
        <td><input type="text" v-model="name" /></td>
      </tr>
      <tr>
        <td>age</td>
        <td>{{ age }}</td>
        <td><input type="text" v-model="age" /></td>
      </tr>
    </table>
    <my-component v-bind:my-name.sync="name" v-bind:my-age.sync="age"></my-component>


  </div>
</template>

<script>
  /**
   * 1.第一种组件的使用
   * import Vue from 'vue'
   var Child = Vue.extend({
    template: '<p>This is a child component!</p>'
  })
   Vue.component('my-component',Child );

   export default {
  name: 'app',
  el: '#app'

}
   */

  /**
   * 2.第二种获取组件的使用
   * import Vue from 'vue'
   var Child = Vue.extend({
    template: '<p>This is a child component!</p>'
  })
   Vue.component('my-component',Child );

   export default {
    name: 'app',
    el: '#app',
    components:{
      'my-component':{
        template: '<p>This is a child component!</p>'
      }
    }

  }
   */

  /**
   * 3.到如组件的使用
   * import Hello from './components/Hello.vue'

   export default {
    name: 'app',
    el: '#app',
    components:{
      'my-component':Hello
    }

  }
   */


  /**
   * 对应test模块
   * import test from './components/test.vue'
   export default {
    el: '#app',
    components: {
      'my-component': test,
    },
    data(){
      return{
        name: 'keepfool',
        age: 28
      }
    },

  }
   */
  import test from './components/test.vue'
  export default {
    el: '#app',
    components: {
      'my-component': test,
    },
    data(){
      return{
        name: 'keepfool',
        age: 28
      }
    },

  }


</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
