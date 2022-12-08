<!--when we build web application the common scenario display the list of item (ex.list of name) repeat the html for each item in the list .
in vue js we archive using v-for directive, (array of string, array of object, array of aaray)-->
<template>
  <div>
    <h2 v-for="(name,index) in names" :key="name">{{index}} {{name}}</h2>
    <h2 v-for="name in fullNames" :key="name.first">{{name.first}} {{name.last}}</h2>
    
    <!-- <h2 v-for="actor in actors" :key="actor.name"></h2>
  <h2>{{actor.name}}</h2>
  <h3 v-for="movie in actor.movies" :key="movie">{{movie}}</h3> -->
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data(){
    return {
      names: ['Tom', 'harry', 'peter'],
      fullNames: [
        {first:'tom',last:'wayne'},
        {first:'harry',last:'kent'},
        {first:'peter',last:'parker'},
    ],
    // actors: [
    //   {
    //     name:'Christian Bale',
    //     movies: ['Batman','The Prestiage'],
    //   },
    //   {
    //     name:'Di Caprio',
    //     movies: ['Titan','The Inception'],
    //   },
    // ],
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
