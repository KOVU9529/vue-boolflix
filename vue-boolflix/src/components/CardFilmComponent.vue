<template>
<!-- Creo la struttura della card -->
<!-- Utilizzo  il nome della props -->
  <div class="cardFilm">
      <div>
          <div>
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
            <h2>{{movie.vote_average}}</h2>
          </div>
        </div>
      </div>
</template>

<script>

export default {
    name:'CardFilmComponent',
    //dichiaro il nome della props
    props:['movie']
}
</script>

<style lang="scss">
.cardFilm{
    background-color: white;
    padding: 10px;
}
</style>>

