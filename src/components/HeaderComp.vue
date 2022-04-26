<template>
    <div>
        <!--inserire contenuto componente-->
        <div>
            Logo
        </div>
        <div class="search">
            <form>
                <input type="text"  placeholder="scrivi il film" v-model="selectFilm" @keydown.enter.prevent="$emit('filmCercato', selectFilm)">
            </form>
            <button type="button" @click.prevent="$emit('filmCercato', selectFilm)">Cerca</button>
        </div>
    </div>
</template>

<script>
    export default {
        //Cambiare il nome con quello del componente creato
        name: 'HeaderComp',
        data(){
            return{
                selectFilm: ''
            }
        }    
    }
</script>

<style scoped lang="scss">
    /*Inserire style componente*/
    div{
        display: flex;
        justify-content: space-between;
        .search{
            display: flex;

        }
    }
</style>