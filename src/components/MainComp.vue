<template>
    <div class="containers">
        <!--inserire contenuto componente-->
        <div class="row py-5 justify-content-around">
            <h2 class="fw-bold text-light"
            :class="( this.arrayFilms == '' ) ? 'd-none' : ''">FILM</h2>
            <FilmCard v-for="element in arrayFilms" :key="element.id" 
                :titolo="element.title"
                :titoloOriginale="element.original_title" 
                :lingua="element.original_language"
                :voto="element.vote_average" 
                :image="element.poster_path" 
                :descrizione="element.overview" />
        </div>
        <div class="row py-5 justify-content-around">
            <h2 class="fw-bold text-light"
            :class="( this.arraySerieTv == '' ) ? 'd-none' : ''">SERIE TV</h2>
            <TvCard v-for="element in arraySerieTv" :key="element.id" 
                :SerieTvTitolo="element.name"
                :SerieTvTitoloOriginale="element.original_name" 
                :SerieTvLingua="element.original_language"
                :SerieTvVoto="element.vote_average" 
                :SerieTvImage="element.poster_path"
                :SerieTvDescrizione="element.overview" />
        </div>
    </div>
</template>

<script>
    import FilmCard from './FilmCard.vue'
    import TvCard from './TvCard.vue'
    export default {
        //Cambiare il nome con quello del componente creato
        name: 'MainComp',
        components: {
            FilmCard,
            TvCard
        },
        props: {
            arrayFilms: Array,
            arraySerieTv: Array

        }

    }
</script>

<style scoped lang="scss">
    /*Inserire style componente*/
    .containers{
        width: 95%;
        margin: 0 auto;
        .row>*{
            padding: 0 !important;
        }
    }
    .d-none{
        display: none;
    }
</style>