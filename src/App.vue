<template>
  <div id="app">
    <header>
      <HeaderComp @filmCercato="metodoFilm" />
    </header>
    <main>
      <MainComp 
      :arrayFilms="filmArray"
      :arraySerieTv="serieTvArray"/>    
    </main>


  </div>
</template>

<script>
  import axios from 'axios'
  import HeaderComp from './components/HeaderComp.vue'
  import MainComp from './components/MainComp.vue'
  


  export default {
    name: 'App',
    components: {
      HeaderComp,
      MainComp
     
    },

    // data
    data() {
      return {
        // chiave API (valore da inserire nell'URL dopo api_key)
        apiKey: '557fc5648782a7ae0abfdf684096fa51',
        // valore della ricerca (valore da inserire nell'URL dopo query)
        filmScelto: '',
        // array dei film
        filmArray: [],
        // array serie tv
        serieTvArray: []
      }
    },

    // metodi con le funzioni
    methods: {
      metodoFilm(selectFilm) {
        this.filmScelto = selectFilm
        console.log(this.filmScelto)

        axios.get(
            `https://api.themoviedb.org/3/search/movie?api_key=${this.apiKey}&language=it-IT&query=${this.filmScelto}`
          )
          .then((res) => {
            console.log(res.data.results)
            this.filmArray = res.data.results
          });

        axios.get(
            `https://api.themoviedb.org/3/search/tv?api_key=${this.apiKey}&language=it-IT&query=${this.filmScelto}`)
          .then((res) => {
            console.log(res.data.results)
            this.serieTvArray = res.data.results
          })
      },

    }
  }
</script>

<style lang="scss">
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app{
  background-color: #1B1B1B;
}
header{
  height: 10vh;
}
main{
  height: 90vh;
  overflow-y: auto;
}
::-webkit-scrollbar{
            display: none;
        }



</style>