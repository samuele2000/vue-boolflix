<template>
    <div class="flip-card my-3 mx-4">
        <div class="flip-card-inner d-flex flex-column justify-content-between">
            <div class="flip-card-front" :style="{ backgroundImage: `url(https://image.tmdb.org/t/p/w342/${image})` }">
                <h4 :class="( `${image}` == null ) ? 'd-block' : ''" class="non-disp">IMMAGINE NON DISPONIBILE</h4>
            </div>
            <div class="flip-card-back p-3 overflow-auto">
                <div class="d-flex align-items-baseline my-1">
                    <h4 class="fs-5">Titolo:</h4>
                    <span class="fs-6 ms-1">{{titolo}}</span>
                </div>
                <div :class="(titoloOriginale == titolo) ? 'd-none' : ''" class="my-1">
                    <span class="fs-5">Titolo orignale:</span>
                    <span class="fs-6 ms-1">{{titoloOriginale}}</span>
                </div>
                <div class="d-flex align-items-center my-1">
                    <h2 class="fs-5">Lingua:</h2>
                    <span :class=" (lingua === 'en') ? 'eng-flag' : (lingua === 'it') ? 'ita-flag' : 'random-flag'"
                        class="flag ms-1">
                    </span>
                </div>
                <div class="my-1">
                    <h4 class="fs-5 ">Voto:</h4>
                    <p :class="(voto >= 1 && voto < 2 ) ? 'una-star' : (voto >= 2 && voto < 4 ) ? 'due-star' : (voto >= 4 && voto < 6) ? 'tre-star' : (voto >= 6 && voto < 8 ) ?     'quattro-star' : (voto >= 8 && voto <= 10) ? 'cinque-star' : 'zero-star'"
                        class="star">
                    </p>
                </div>
                <div :class="(descrizione == '') ? 'd-none' : ''" class="my-1">
                    <h4 class="fs-5">Descrizione:</h4>
                    <p>{{descrizione}}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        //Cambiare il nome con quello del componente creato
        name: 'FilmCard',
        props: {
            titolo: String,
            titoloOriginale: String,
            lingua: String,
            voto: Number,
            image: String,
            descrizione: String
        }
    }
</script>

<style scoped lang="scss">
@import '../style/mixin.scss';
    /*Inserire style componente*/
    //stile card 
    @include flipCard;
    //fine stile card

    .non-disp{
        background-color: rgba(0, 0, 0, 0.8);
        color: white;
        height: 100%;
        text-align: center;
        display: flex;
        align-items: center;
        display: none;
    }
    .d-block{
        display: block;
    }
    .d-none {
        display: none;
    }

    //bandiere
    .flag {
        width: 48px;
        height: 48px;
        background-repeat: no-repeat;
        background-size: contain
    }

    .ita-flag {
        background-image: url(../assets/img/icons8-italia-48.png);
    }

    .eng-flag {
        background-image: url(../assets/img/icons8-gran-bretagna-48.png);
    }

    .random-flag {
        background-image: url(../assets/img/icons8-mappamondo-48.png);
    }

    // valutazione con stelle 
    .star {
        width: 100px;
        height: 48px;
        background-repeat: no-repeat;
        background-size: contain;
    }

    .zero-star {
        background-image: url(../assets/img/Stelle-valutazione/zero-stelle.png);
    }

    .una-star {
        background-image: url(../assets/img/Stelle-valutazione/una-stella.png);
    }

    .due-star {
        background-image: url(../assets/img/Stelle-valutazione/due-stelle.png);
    }

    .tre-star {
        background-image: url(../assets/img/Stelle-valutazione/tre-stelle.png);
    }

    .quattro-star {
        background-image: url(../assets/img/Stelle-valutazione/quatrro-stelle.png);
    }

    .cinque-star {
        background-image: url(../assets/img/Stelle-valutazione/cinque-stelle.png);
    }
</style>