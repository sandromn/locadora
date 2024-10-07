<script setup>



  const filmes = reactive( [
     {
      id: 0,
      nome: "Elissium",
      preco:  80.00,
      alugado: false,
    },
     {
      id: 1,
      nome: "Alien 4",
      preco:  20.00,
      alugado: false,
    },
    {
      id: 2,
      nome: "Interistellar",
      preco:  110.00,
      alugado: true,
    },

])

function alteraAlugado(id){
  filmes[id].alugado = true;
}

</script>

<template>
 
  <Cabecalho/>

  <hr/>
  <p><strong>Filmes recomendados:</strong></p>

  <div class="conteudo">
        
    <Filme v-for="filme in filmes" v-bind:filme="filme" v-bind:alteraAlugado="alteraAlugado" />
    
  </div>

</template>

<style>

  .conteudo{
    display: flex;
    gap: 20px;

  }
</style>
