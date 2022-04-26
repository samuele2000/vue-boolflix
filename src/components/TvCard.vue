<template>
    <div>     
        <ul>
            <li>
                <h4>{{SerieTvTitolo}}</h4>
            </li>
            <li>
                <h4>{{SerieTvTitoloOriginale}}</h4>
            </li>
            <li>
                <h4 :class=" (SerieTvLingua === 'en') ? 'eng-flag' : (SerieTvLingua === 'it') ? 'ita-flag' : 'random-flag'" class="flag"></h4>
            </li>
            <li>
                <h2 :class="(SerieTvVoto >= 1 && SerieTvVoto < 2 ) ? 'una-star' : (SerieTvVoto >= 2 && SerieTvVoto < 4 ) ? 'due-star' : (SerieTvVoto >= 4 && SerieTvVoto < 6) ? 'tre-star' : (SerieTvVoto >= 6 && SerieTvVoto < 8 ) ? 'quattro-star' : (SerieTvVoto >= 8 && SerieTvVoto <= 10) ? 'cinque-star' : 'zero-star'" class="star"></h2>
            </li>
            <li>
                <img :src="`https://image.tmdb.org/t/p/w185/${SerieTvImage}`" alt="">
            </li>
            
        </ul>    
    </div>    
</template>

<script>
    export default {
        //Cambiare il nome con quello del componente creato
        name: 'TvCard',
        props:{
            SerieTvTitolo: String,
            SerieTvTitoloOriginale: String,
            SerieTvLingua: String,
            SerieTvVoto: Number,
            SerieTvImage: String,
            SerieTvDescrizione: String
        } 
    }
</script>

<style scoped lang="scss">
    /*Inserire style componente*/
   .flag{
        width: 48px;
        height: 48px;
        background-repeat: no-repeat;
        background-size: contain;
    }
    .star{
        width: 100px;
        height: 48px;
        background-repeat: no-repeat;
        background-size: contain; 
    }
    .ita-flag{
        background-image: url(../assets/img/icons8-italia-48.png);
    }
    .eng-flag{
        background-image: url(../assets/img/icons8-gran-bretagna-48.png);
    }
    .random-flag{
        background-image: url(../assets/img/icons8-mappamondo-48.png);
    }
     .zero-star{
        background-image: url(../assets/img/Stelle-valutazione/zero-stelle.png);
    }
    .una-star{
        background-image: url(../assets/img/Stelle-valutazione/una-stella.png);
    }
    .due-star{
        background-image: url(../assets/img/Stelle-valutazione/due-stelle.png);
    }
    .tre-star{
        background-image: url(../assets/img/Stelle-valutazione/tre-stelle.png);
    }
    .quattro-star{
        background-image: url(../assets/img/Stelle-valutazione/quatrro-stelle.png);
    }
    .cinque-star{
        background-image: url(../assets/img/Stelle-valutazione/cinque-stelle.png);
    }
   
</style>