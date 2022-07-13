<template>
  <div id="app">
    <!--riporto il emit-->
    <HeaderComponent @getInputFilm="getInput" />
    <!--riporto il componente con la props-->
    <FilmList :moviesArray="moviesArray" />
  </div>
</template>

<script>
//importo axios
import axios from 'axios';
//importo i componeneti
import HeaderComponent from './components/HeaderComponent.vue';
import FilmList from './components/FilmList.vue';

export default {
  name: 'App',
  components: {
    HeaderComponent,
    FilmList
  },
  data(){
    return{
      //per il funzionamento api (chiave personale)
      apiKEY:'22417c572e70c5c8b4a73abbcd09085a',
      //url inizialmente generico
      apiURL:'https://api.themoviedb.org/3/search/',
      //array inizialmente vuoto
      //successivamente popolato alla chiamata
      moviesArray:[ ],
    }
  },
  methods:{
    //funzione per prendere il parametro dell'emit 
    getInput(searchFilm){
      //chiamata api con valori aggiornati
      axios.get(`${this.apiURL}movie?api_key=${this.apiKEY}&query=${searchFilm}`)
      .then((response)=>{
      //l'array inizialmente vuoto si popola alla chiamata
      this.moviesArray=response.data.results;
    })
    }
  }
}
</script>

<style lang="scss">
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body{
  background-color: rgb(23, 23, 23);
}
</style>