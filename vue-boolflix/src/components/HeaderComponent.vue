<template>
  <div class="header">
      <div>
          <h1>BOOLFLIX</h1>
      </div>
      <nav>
          <!--imposto il v-model per ottenere il valore della input-->
          <input v-model="searchFilm" type="text">
          <!--imposto la funzione al click-->
          <button  @click="filmSearch">
            Search 
          </button>
      </nav>
      <div class="user">
          <div  class="profilePic">
              <img class="eyes" src="../assets/img/occhi.jpeg" alt="">
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
h1{
    color: rgb(160, 18, 18);
}
input{
    background-color: rgb(160, 18, 18);
    border-radius:20px 0 0 20px ;
    border: none;
    padding: 5px;
    color: white;
    clear: inherit;
}
button{
    background-color: rgb(160, 18, 18);
    border: none;
    border-radius: 0 20px 20px 0 ;
    padding: 5px;
    color: white;
}
.user{
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100px;
    height: 100px;
    .profilePic{
        border-radius: 50%;
        width: 70px;
        height: 70px;
        background-color: white;
        position: relative;
        .eyes{
            position: absolute;
            width: 100%;
            height: 100%;
            border-radius: 50%;
        }
    }
}
}
</style>

