<!--when we build web application the common scenario display the list of item (ex.list of name) repeat the html for each item in the list .
in vue js we archive using v-for directive, (array of string, array of object, array of aaray)-->
    <!-- <ul>
      <li v-for="(name,index) in names" :key="name">{{index}} {{name}}</li>
    </ul>
    
    <h2 v-for="name in fullNames" :key="name.first">{{name.first}} {{name.last}}</h2>
     -->
    <!-- <h2 v-for="actor in actors" :key="actor.name"></h2>
  <h2>{{actor.name}}</h2>
  <h3 v-for="movie in actor.movies" :key="movie">{{movie}}</h3> -->
  <template>
    <div id="app">
      <input type="text" v-model="newMovie">
      <button id="btn" @click="addMovie">add movie</button>
      <ul id="mov">
        <li id="movi" v-for="movie in movies" :key="movie">{{ movie }}</li>
      </ul>
      <div id="ing" v-for="(ingredient, index) in ingredients" :key="'ing'+index">
      <div id="title">{{ingredient.title}}</div>
      <div id="price">{{ingredient.price}}</div>
    </div>
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data: () => {
    return {
      movies: ['Batman', 'Spiderman', 'CaptainAmerica', 'X-man'],
      ingredients: [
        {title:'Apple',price:'0.99'},
        {title:'Orange',price:'1.99'},
        {title:'Banana',price:'2.99'},
        {title:'Plum',price:'3.99'},
        {title:'Fig',price:'4.99'},
        
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
  methods: {
    addMovie() {
      if(this.newMovie !== '')
      this.movies.push(this.newMovie);

      this.newMovie = '';
    }
  }
}
</script>

<style>
#body {
  margin-top: 0px;
  padding: 0px;
  font-family: 'Segoe UI, Tahoma';
  font-size: 1rem
}
#app{
  display: flex;
  justify-content: flex-start;
  align-items: center;
  flex-direction: column;
  padding: 10px;
  width: calc(100% -20px);
  height: calc(100vh - 20px);
  color: #fff;
  background-color: #333;
}
#mov {
  margin: 0;
  padding: 0;
  list-style: none;
}
#movi{
display: inline-block;
padding: 10px;
  }
#ing {
    padding: 8px 20px 2px;
    width: calc(100% - 500px);
    height: 40px;
    border-top: 1px solid #ddd;
  }
#title { float: left; padding-top: 8px; }
#price {float: right; padding-top: 8px ;}
#btn{
  margin-top: 10px;
}
</style>
