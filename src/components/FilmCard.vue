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
                <h2>{{voto}}</h2>
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