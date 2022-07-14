<template>
<div class="list">
    <!--imposto il ciclo v-for con gli elementi passati tramite props-->
    <div class="film e serie" :key="movie.id"
         v-for="movie in filmSerieArray ">
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
        filmSerieArray:Array
    },
    components:{
        CardFilmComponent,
    }
}
</script>

<style lang="scss" scoped>
.list{
    display: flex;
    flex-direction: row;
    overflow: scroll;
    padding: 30px;
    height: 100vh;
    width: 100%;
}
</style>

