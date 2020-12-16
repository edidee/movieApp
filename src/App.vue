<template>
  <div id="app">
    <Header />
    <Body v-bind:info="movie" @submit="finished($event)" />
    <Footer />
    
  </div>
</template>

<script>
import Header from './components/Header';
import Body from './components/Body'
import Footer from './components/Footer';

export default {
  name: 'App',
  components: {
    Header,
    Body,
   Footer,
  },

  data () {
    return {
      movie: {}, 
      baseURL : 'https://api.themoviedb.org/3/search/movie?api_key=dccdd23fa085a81162820018e4b54d15'
    }
  },

  methods: {
    async getMovies () {
       try{
         const { data } = await this.$http.get(this.baseURL)
         this.movie = data
        console.log(data)
       } 
       catch(err){
         console.log(err)
       }
      
     
    },

     finished(updated) {
     let input= this.$refs = updated; 
    const readyUrl = this.baseURL+ '&query=' + input;
    return readyUrl
  }
  },
  mounted() {
    this.getMovies()
  },

  
}
</script>

<style>
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  
  
}
</style>
