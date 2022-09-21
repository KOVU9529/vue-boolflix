<template>
<div>
    <div class="header">
      <div>
          <h1>BOOLFLIX</h1>
      </div>
      <nav>
          <!--imposto il v-model per ottenere il valore della input-->
          <input v-model="searchFilm" type="text">
          <!--imposto la funzione al click-->
          <button  @click="filmSearch">
            BOOLFLIX 
          </button>
      </nav>
      <div class="user">
          <div  class="profilePic">
              <img class="eyes" src="../assets/img/occhi.jpeg" alt="">
          </div>
      </div>
  </div>
  <div class="jumbotron">
      <h2>
          Serie Evento
      </h2>
      <h3>
          HOUSE OF DRAGON
      </h3>
      <p>
          House of the Dragon è una serie tv statunitense spin-off e prequel della popolarissima Il Trono di Spade, 
          anche conosciuta con il titolo Game of Thrones. Basato anch'esso su un romanzo dello scrittore George R.R. Martin, Fuoco e sangue,
           che precede appunto gli eventi delle Cronache del ghiaccio e del fuoco, il drama fantasy è ambientato 172 anni prima dei sanguinosi fatti della serie originale e racconta gli eventi che hanno portato alla rovinosa caduta e alla fine del dominio di Casa Targaryen; fino alla cosiddetta Danza dei Draghi, il conflitto civile scoppiato nei Sette Regni tra due rami della stessa casa.
          Seguiamo Viserys I Targaryen (interpretato dall'attore di The Outsider Paddy Considine), il quinto re dei Sette Regni, conosciuto come un uomo cordiale, gentile e onesto, scelto da un consiglio di lord per succedere a suo nonno Jaehaerys I Targaryen. La Principessa Rhaenyra Targaryen (Emma D'Arcy, Truth Seekers), primogenita di Re Viserys, è una cavalca draghi che si aspetta di diventare la prima regina regnante dei Sette Regni, ma viene messa in discussione dal fratellastro più giovane, Aegon II Targaryen (Tom Glynn-Carney, Domina). Il Principe Daemon Targaryen (Matt Smith, The Crown), presunto erede al Trono di Spade, è il fratello minore di Viserys e lo zio di Rhaenyra. Un guerriero impareggiabile e un esperto cavalca draghi, Daemon brandisce la spada in acciaio di Valyria chiamata Sorella Oscura, consegnatagli da Jaehaerys.
          Il resto del cast include Rhys Ifans (Berlin Station) nel ruolo di Ser Otto Hightower, il Primo Cavaliere del Re e un acerrimo rivale politico del Principe Daemon; Olivia Cooke (Bates Motel) della figlia del cavaliere, Alicent Hightower, cresciuta nella Fortezza Rossa e conosciuta come la donna più attraente del regno; Steve Toussaint (Berlin Station) di Lord Corlys Velaryon, signore dell'omonima casa, conosciuto come il Serpente di Mare perché il più famoso marinaio nella storia di Westeros; Eve Best (Nurse Jackie) della Principessa Rhaenys Targaryen, moglie di Lord Corlys, una cavalca draghi che un tempo era candidata a succedere a suo nonno Jaehaerys come sovrana dei Sette Regni ma fu messa da parte in favore di suo cugino Viserys; Fabien Frankel di Ser Criston Cole, un abile spadaccino delle Terre della Tempesta; e Sonoya Mizuno (Devs) di Lady Mysaria, 
          una ballerina del Continente Orientale diventata l'alleato (e non solo questo) più fidato del Principe Daemon.
      </p>
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
    width: 90px;
    height: 90px;
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
.jumbotron{
    background-color: orange;
    color: rgba(160, 18, 18, 0.8);
    font-size: 30px;
    width:100%;
    height: 600px;
    background-image: url(../assets/img/house-of-dragon.jpeg);
    background-size: cover;
    background-position:initial;
    background-position-y:-100px;
    p{
        opacity: 0;
        height: 300px;
    }
    p:hover{
        padding: 20px;
        color: rgb(218, 210, 210);
        opacity: 1;
        background-image: url(../assets/img/house-of-dragon.jpeg);
        background-size: cover;
        background-position:initial;
        overflow: scroll;
    }
}
</style>

