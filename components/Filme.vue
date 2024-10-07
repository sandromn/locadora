<script setup>

    // pega os parametros que foram passados
    // const params = useAttrs(); pega so uma variavel
    const params = defineProps(["filme", "alteraAlugado"]); // pega todo o objeto

</script>

<template>

    <div class="conteudo">
        <p>{{ params.filme.nome }}</p>
        <p v-if="params.filme.alugado == true"><u>alugado</u> </p> 
  <img src="https://placeholder.co/150"/>
  <p> R$ {{ params.filme.preco }}</p>
  <button v-on:click="params.alteraAlugado(params.filme.id)" v-if="params.filme.alugado == false" class="button">Alugar</button>
  
    </div>
    
    

</template>

<style scoped>

.conteudo{

    display: flex;
    flex-direction: column;
    width: 200px;
    text-align: center;
    background-color: blueviolet;
    padding: 15px;
    color: #fff;
    gap: 10px;
    border-radius: 10px;


        
    }

    .button{
        background-color: orange;
        padding: 15px;
        color: #fff;
        border: none;
    }

</style>

    