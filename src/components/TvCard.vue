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
                <h4>{{SerieTvVoto}}</h4>
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
    .ita-flag{
        background-image: url(../assets/img/icons8-italia-48.png);
    }
    .eng-flag{
        background-image: url(../assets/img/icons8-gran-bretagna-48.png);
    }
    .random-flag{
        background-image: url(../assets/img/icons8-mappamondo-48.png);
    }
   
</style>