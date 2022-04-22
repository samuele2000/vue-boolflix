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
                <h2>{{lingua}}</h2>
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
   
</style>