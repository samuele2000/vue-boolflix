<template>
  <div>
    <header>
      <HeaderComp @filmCercato="metodoFilm" />
    </header>
    <main>
      <FilmCard v-for="element in filmArray" :key="element.id" 
        :titolo="element.title"
        :titoloOriginale="element.original_title" 
        :lingua="element.original_language" 
        :voto="element.vote_average" />

      <TvCard v-for="element in serieTvArray" :key="element.id" 
        :SerieTvTitolo="element.name"
        :SerieTvTitoloOriginale="element.original_name" 
        :SerieTvLingua="element.original_language" 
        :SerieTvVoto="element.vote_average" />
    </main>


  </div>
</template>

<script>
  import axios from 'axios'
  import HeaderComp from './components/HeaderComp.vue'
  import FilmCard from './components/FilmCard.vue'
  import TvCard from './components/TvCard.vue'


  export default {
    name: 'App',
    components: {
      HeaderComp,
      FilmCard,
      TvCard
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

</style>