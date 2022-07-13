<template>
<div class="list">
    <!--imposto il ciclo v-for con gli elementi passati tramite props-->
    <div :key="movie.id"
         v-for="movie in moviesArray ">
         <!--nome componente :nome nel figlio="valore che voglio passare"-->
         <CardFilmComponent :movie="movie"/>
    </div>
</div>
  
</template>

<script>
import CardFilmComponent from './CardFilmComponent.vue';

export default {
    name:'FilmList',
    props:{
        //dichiaro la props
        moviesArray:Array
    },
    components:{
        CardFilmComponent,
    }
}
</script>

<style lang="scss" scoped>
.list{
    padding: 20px;
}
</style>

