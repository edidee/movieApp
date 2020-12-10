<template>
  <div id="app">
    <Header />
    
  </div>
</template>

<script>
import Header from './components/Header'


export default {
  name: 'App',
  components: {
    Header,
   
  },

  data () {
    return {
      movie: {},
      
    }
  },

  methods: {
    getMovies: function () {
      const baseURL = 'http://www.omdbapi.com/?i=tt3896198&apikey=42a545b2'
      this.$http.get(baseURL)
      .then(response => {
        this.movie = response.body
        console.log(response)
      })
      .catch(error => {
        console.log(error)
      })
    }
  }




  
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
