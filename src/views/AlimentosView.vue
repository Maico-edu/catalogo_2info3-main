<script setup>
import { ref } from 'vue'
import { listaProdutos } from '@/data/produtos';
import { formataPreco } from '@/utils/produtoUtils';
import produtoCard from '@/components/produtoCard.vue';

const produtos = ref(listaProdutos)
produtos.value = produtos.value.filter(p => p.categoria === 'Alimentos');

</script>

<template>
    <div class="container">
        <h1>Alimentos</h1>
        <div class="produtos">
            <produto-card v-for="produto in produtos" :key="produtos.id" :id="produto.id" :nome="produto.nome" 
            :preco="produto.preco" :categoria="produto.categoria" :imagem="produto.imagem">

            </produto-card>
        </div>
    </div>
</template>

<style scoped>
   .produto-card {
        display: flex;
        align-items: center;
        justify-content: space-between;
        border: 1px solid #ccc;
        padding: 16px;
        margin-bottom: 16px;
    }

</style>