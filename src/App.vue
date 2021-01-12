<template>
  <div id="app">
    <!-- <img src="./assets/logo.png"> -->
    
      <tr v-for="item in data" :key="item.id">
        <td>userId : {{item.userId}}</td>
        <td>id : {{item.id}}</td>
        <td>title : {{item.title}}</td>
        <td>completed : {{item.completed}}</td>
      </tr>
    <!-- <HelloWorld/> -->
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'

export default {
  name: 'App',
  data (){
    return {
      data:{},

    }
  },
  components: {
    HelloWorld
  },
  created(){
    const api = "https://jsonplaceholder.typicode.com/todos";
    this.$http.get(api).then((response) => {
      this.data = response.data;
    })
  }
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

tr,td{
  border: 1px solid black;
  border-collapse:collapse;
}
</style>
