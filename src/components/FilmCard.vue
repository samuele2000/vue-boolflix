<template>
    <div>
        <ul>
            <li>
                <h2>{{titolo}}</h2>
            </li>
            <li>
                <h2>{{titoloOriginale}}</h2>
            </li>
            <li>
                <h2 :class=" (lingua === 'en') ? 'eng-flag' : (lingua === 'it') ? 'ita-flag' : 'random-flag'" class="flag"></h2>
            </li>
            <li>
                <h2 :class="(voto >= 1 && voto < 2 ) ? 'una-star' : (voto >= 2 && voto < 4 ) ? 'due-star' : (voto >= 4 && voto < 6) ? 'tre-star' : (voto >= 6 && voto < 8 ) ? 'quattro-star' : (voto >= 8 && voto <= 10) ? 'cinque-star' : 'zero-star'" class="star"></h2>
            </li>
            <li>
                <img :src="`https://image.tmdb.org/t/p/w185/${image}`" alt="">
            </li>
            
        </ul>
    
    </div>
</template>

<script>
    export default {
        //Cambiare il nome con quello del componente creato
        name: 'FilmCard',
        props:{
            titolo: String,
            titoloOriginale: String,
            lingua: String,
            voto: Number,
            image: String,
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