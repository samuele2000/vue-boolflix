<template>
    <div class="d-flex justify-content-between align-items-center">
        <!--inserire contenuto componente-->
        <div class="ms-3">
            <h class="text-danger fw-bold fs-1">BOOLFLIX</h>
        </div>
        <div class="d-flex me-3">
            <input type="text"  placeholder="scrivi il film" v-model="selectFilm" @keydown.enter.prevent="$emit('filmCercato', selectFilm)" class="input-group-text py-1">   
            <button type="button" class="btn btn-danger ms-2" @click.prevent="$emit('filmCercato', selectFilm)"><i class="fa-solid fa-magnifying-glass text-light"></i></button>
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

</style>