<template>
  <div id="app" class= 'container'>
    <img src="./assets/logo.png" class = 'logo'>
    <todo-list> </todo-list>
    <HelloWorld> </HelloWorld>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import TodoList from './components/TodoList.vue';


export default {
  name: 'App',
  components: {
    HelloWorld,
    TodoList,
  }
}
</script>

<style>
*{
  box-sizing: border-box;
}

.container {
  max-width: 600px;
  margin: 0 auto;
}

#app {
  font-family: 'Muli', Arial, sans-serif;
  font-style: normal;
  font-display: swap;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
  font-size: 20px ;
  src: url(https://fonts.gstatic.com/s/muli/v29/7Aulp_0qiz-aVz7u3PJLcUMYOFnOkEk40eiNxw.woff2) format('woff2');
  unicode-range: U+0102-0103, U+0110-0111, U+0128-0129, U+0168-0169, U+01A0-01A1, U+01AF-01B0, U+0300-0301, U+0303-0304, U+0308-0309, U+0323, U+0329, U+1EA0-1EF9, U+20AB;

}



.logo {
  display: block ;
  margin: 20px auto;
  height: 120px;
}

</style>
