<template>
    <div>
        <!--inserire contenuto componente-->
        <div class="films">
            <FilmCard v-for="element in arrayFilms" :key="element.id" 
                :titolo="element.title"
                :titoloOriginale="element.original_title" 
                :lingua="element.original_language"
                :voto="element.vote_average" 
                :image="element.poster_path" 
                :descrizione="element.overview" />
        </div>
        <!-- <div>
            <TvCard v-for="element in arraySerieTv" :key="element.id" 
                :SerieTvTitolo="element.name"
                :SerieTvTitoloOriginale="element.original_name" 
                :SerieTvLingua="element.original_language"
                :SerieTvVoto="element.vote_average" 
                :SerieTvImage="element.poster_path"
                :SerieTvDescrizione="element.overview" />
        </div> -->
    </div>
</template>

<script>
    import FilmCard from './FilmCard.vue'
    //import TvCard from './TvCard.vue'
    export default {
        //Cambiare il nome con quello del componente creato
        name: 'MainComp',
        components: {
            FilmCard,
            // TvCard
        },
        props: {
            arrayFilms: Array,
            arraySerieTv: Array

        }

    }
</script>

<style scoped lang="scss">
    /*Inserire style componente*/
    .films{
        display: flex;
        flex-wrap: wrap;
    }
    
</style>