<script setup>
    const categorias =[
        { nome: "ação"},
        { nome: "suspense"},
        { nome: "Terror"},
        { nome: "Dorama"},
        { nome: "Comédia"},
        { nome: "Romance"},
        { nome: "Documentário"},
        { nome: "Drama"},
    ]
</script>

<template>
    <h1> Categorias de filmes</h1>
    <div v-for="categoria in categorias">
        
    </div>
 
        
</template>