<template>
<!-- Creo la struttura della card -->
<!-- Utilizzo  il nome della props -->
  <div class="cardFilm">
      <div class="imgDisplay">
            <div>
                <!--Millestone 3 struttura creazione immagine=
                    urlGENERICO Immagini + dimensioni + specifico url img -->
                <img  :src="apiURL + 'w500'+ `${movie.backdrop_path}`" alt="">
            </div>
        <div class="information">
            <div >
            <h2>Titolo</h2>
            <h2>{{movie.title}}</h2>
          </div>
          <div>
            <h2>Titolo</h2>
            <h2>{{movie.original_title}}</h2>
          </div>
          <div>
            <h2>Lingua</h2>
            <h2>{{movie.original_language}}</h2>
          </div>
          <div>
            <h2>Voto</h2>
            <!--Millestone 3
            Dopo aver importato la cdn, 
            imposto il ciclo v-for per associare 
            il voto al numero di stelle-->
            <i :key="index" v-for="(item,index) in numberVote" class="fa-solid fa-star" ></i>
          </div>  
        </div>
        </div>
    </div>
</template>

<script>
export default {
    name:'CardFilmComponent',
    //dichiaro il nome della props
    props:['movie'],
    data(){
        return{
            //Creo apiURL per riportarmi il valore delle img generiche
            apiURL:'https://image.tmdb.org/t/p/',
            numberVote:0,
        }
    },
    //converto il formato numerico iniziale decimale (da 1 a 10) => 
    //formato numerico finale intero (da 1 a 5) 
   created(){
   this.numberVote=Math.ceil(this.movie.vote_average / 2); 
   console.log(this.numberVote);
   }
}
</script>

<style lang="scss">
.cardFilm{
    
    padding: 10px 0;
    position: relative;
  
    .imgDisplay{
        opacity: 1;
        z-index: 3;
    }
    .imgDisplay:hover .information{
        opacity: 1;
    }
    .information{
        padding: 10px;
        position: absolute;
        top: 3%;
        width: 500px;
        height: 282px;
        background-color: black;
        opacity: 0;
        color: white;
        i{
        color: yellow;
    }
    }
}
</style>

