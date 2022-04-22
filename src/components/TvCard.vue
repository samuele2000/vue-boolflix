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
                <h4>{{SerieTvLingua}}</h4>
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
   
</style>