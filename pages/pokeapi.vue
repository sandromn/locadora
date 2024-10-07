<script setup>

import axios from "axios";

let dados = ref(); //campo para input, criar cada campo//
let digitado =ref("");

    async function buscaTodos(){
        let resposta = await axios.get("https://pokeapi.co/api/v2/pokemon/squirtle")
        console.log(resposta);

        dados.value = resposta.data;
    }

    async function pesquisar(){
        let resposta = await axios.get("https://pokeapi.co/api/v2/pokemon/"+digitado.value)
        console.log(resposta);

        dados.value = resposta.data;
    }

    
    onMounted(()=>{
        
        buscaTodos();

    })


</script>

<template>
    <h1>Consulta na API do Pokémon</h1>

    <input v-model="digitado" placeholder="Digite o nome de um Pokémon"  size="30"/>
    <button v-on:click="pesquisar" >Pesquisar</button>

    <div v-if="dados != null" >

        <p> <strong>  {{ dados.name }}</strong> </p> 

        <ul>
                <li>Id:  {{ dados.id }}</li>
                <li>Habilidade:  {{ dados.abilities[0].ability.name }}</li>
                
        </ul>
        <img v-bind:src="dados.sprites.front_default"/>
        
        

</div>
    
</template>