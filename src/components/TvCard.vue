<template>
    <div class="flip-card my-3 mx-4">
        <div class="flip-card-inner">
            <div class="flip-card-front" :style="{ backgroundImage: `url(https://image.tmdb.org/t/p/w342/${SerieTvImage})` }">
                <h4 :class="( SerieTvImage == null ) ? 'd-block' : ''" class="non-disp">IMMAGINE NON DISPONIBILE</h4>
            </div>
            <div class="flip-card-back p-3 overflow-auto">
                <div class="d-flex align-items-baseline">
                    <h4 class="fs-5">Titolo:</h4>
                    <span class="fs-6 ms-1">{{SerieTvTitolo}}</span>
                </div>
                <div :class="(SerieTvTitoloOriginale == SerieTvTitolo) ? 'd-none' : ''" >
                    <span class="fs-5 fw-bold">Titolo orignale:</span>
                    <span class="fs-5">{{SerieTvTitoloOriginale}}</span>
                </div>
                <div class="d-flex align-items-center">
                    <h2 class="fs-5">Lingua:</h2>
                    <span :class=" (SerieTvLingua === 'en') ? 'eng-flag' : (SerieTvLingua === 'it') ? 'ita-flag' : 'random-flag'"
                        class="flag ms-1">
                    </span>
                </div>
                <div>
                    <h4 class="fs-5 ">Voto:</h4>
                    <p :class="(SerieTvVoto >= 1 && SerieTvVoto < 2 ) ? 'una-star' : (SerieTvVoto >= 2 && SerieTvVoto < 4 ) ? 'due-star' : (SerieTvVoto >= 4 && SerieTvVoto < 6) ? 'tre-star' : (SerieTvVoto >= 6 && SerieTvVoto < 8 ) ?     'quattro-star' : (SerieTvVoto >= 8 && SerieTvVoto <= 10) ? 'cinque-star' : 'zero-star'"
                        class="star">
                    </p>
                </div>
                <div :class="(SerieTvDescrizione == '') ? 'd-none' : ''">
                    <h4 class="fs-5">Descrizione:</h4>
                    <p>{{SerieTvDescrizione}}</p>
                </div>
            </div>
        </div>
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
@import '../style/mixin.scss';
    /*Inserire style componente*/
    //stile card
    @include flipCard;

    .non-disp{
        background-color: rgba(0, 0, 0, 0.8);
        color: white;
        height: 100%;
        text-align: center;
        display: flex;
        align-self: center;
        display: none;
    }
    .d-block{
        display: block;
    }
    .d-none{
        display: none;
    }
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