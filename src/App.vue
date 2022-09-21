<script>
  import axios from 'axios';
  export default {
    data() {
      return{
       cep: "",
       endereco: {},
      };
      }, 
    methods: {
      async buscar() {
        const url = `https://viacep.com.br/ws/${this.cep}/json/`;
        const res = await axios.get(url);
        this.endereco = res.data;
      },
    },
};
</script>
<template>
  <div class="aa">
  <h1>Busca Sees</h1>
  <form @submit.prevent="buscar">
    <input type="text" v-model="cep" placeholder="00000-000">
    <button type="submit">Busca ae</button>
  </form>

  <form class="end">
  Rua:<label for="rua" placeholder="Rua" ></label><input type="text" v-model="endereco.logradouro"/>
  Bairro:<label for="rua" placeholder="Bairro"></label><input type="text" v-model="endereco.bairro"/>
  Cidade:<label for="rua" placeholder="Cidade"></label><input type="text" v-model="endereco.localidade"/>
  UF:<label for="rua" placeholder="Estado"></label><input type="text" v-model="endereco.uf"/>
  </form>  
  </div>
</template>
<style>
div{
  text-align: center;
  justify-content: center;
  margin: 20px;
}
input {
  width: 1000px;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
  box-shadow: rgba(50, 50, 93, 0.25) 0px 2px 5px -1px, rgba(0, 0, 0, 0.3) 0px 1px 3px -1px;
}
button {
  width: 100px;
  background-color: #4CAF50;
  color: white;
  padding: 14px 20px;
  margin: 8px 0;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  box-shadow: rgba(50, 50, 93, 0.25) 0px 2px 5px -1px, rgba(0, 0, 0, 0.3) 0px 1px 3px -1px;

}
button:hover {
  background-color: #45a049;
}
  </style>
