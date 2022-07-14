<template>
<!-- Creo la struttura della card -->
<!-- Utilizzo  il nome della props -->
  <div class="cardFilm">
      <div class="cardisplay">
            <div>
                <!--Millestone 3 struttura creazione immagine=
                    urlGENERICO Immagini + dimensioni + specifico url img -->
                <img class="img" :src="apiURL + 'w342'+ `${movie.backdrop_path}`" alt="">
            </div>
        <div class="information">
            <div >
            <h2 class="red">Titolo</h2>
            <h2>{{movie.name}}{{movie.title}}</h2>
          </div>
          <div>
            <h2 class="red">Titolo</h2>
            <h2>{{movie.original_name}}{{movie.original_title}}</h2>
          </div>
          <div>
            <!--Millestone 2
            imposto le condizioni per la visibilità della lingua
            n.b. utilizzo require per rendere accessibile l'immagine-->
            <h2 class="red">Lingua</h2>
            <img v-if="weFlag.includes(movie.original_language)" class="flag" :src="require(`../assets/img/${movie.original_language}.png`)" alt="">
            <h2 v-else >{{movie.original_language}}</h2>
          </div>
          <div>
            <h2 class="red">Voto</h2>
            <!--Millestone 3
            Dopo aver importato la cdn, 
            imposto il ciclo v-for per associare 
            il voto al numero di stelle-->
            <i :key="index" v-for="(item,index) in numberVote" class="fa-solid fa-star" ></i>
          </div>  
          <div>
              <h2 class="red">
                  Trama
              </h2>
              <h2>
                 {{movie.overview}} 
              </h2>
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
            //creo l'array per associare la selezione delle bandiere
            weFlag:['it','en','fr','es'],
            //Creo apiURL per riportarmi il valore delle img generiche
            apiURL:'https://image.tmdb.org/t/p/',
            //imposto la varaibile numerica
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
    .flag{
        width: 25px;
    }
    .red{
        color: rgb(160, 18, 18);
    }
    .cardisplay{
        opacity: 1;
        z-index: 3;
        .img{
            width: 400px;
            height: 700px;
            object-position: center;
            object-fit:cover;
        }
    }
    .cardisplay:hover .information{
        opacity: 1;
    }
    .information{
        padding: 10px;
        position: absolute;
        top: 10px;
        width: 400px;
        height: 700px;
        background-color: rgb(23, 23, 23);
        opacity: 0;
        color: white;
        i{
        color: yellow;
    }
    }
}
</style>

