<template>
  <div class="header">
      <div>
          <h1>BOOLFLIX</h1>
      </div>
      <nav>
          <!--imposto il v-model per ottenere il valore della input-->
          <input v-model="searchFilm" type="text">
          <!--imposto la funzione al click-->
          <button  @click="filmSearch"
                   > Search </button>
      </nav>
      <div class="user">
          <div  class="profilePic">
          </div>
      </div>
  </div>
</template>

<script>
export default {
    name:'HeaderComponent',
    data(){
        return{
            //variabile utilizzata per il valore della input
            searchFilm:''
        }
    },
    methods:{
     filmSearch(){
          this.$emit('getInputFilm',this.searchFilm)
          //console.log(this.searchFilm);
        }
    }
}
</script>

<style lang="scss" scoped>
.header{
    background-color: black;
    display: flex;
    justify-content: space-between;
    align-items: center;
}
h1{
    color: rgb(160, 18, 18);
}
.user{
    display: flex;
    justify-content: center;
    align-items: center;
    width: 20px;
    height: 20px;
    background-color: rgb(160, 18, 18);
    .profilePic{
        border-radius: 50%;
        width: 10px;
        height: 10px;
        background-color: white;
    }
}

</style>

