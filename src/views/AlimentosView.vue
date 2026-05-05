<script setup>
import { ref } from 'vuw'
import { listaProdutos } from '@/data/produtos';
const produtos = ref(listaProdutos)
produtos.value = produtos.value.filter(p => p.categoria === 'alimentos');

</script>

<template>

</template>

<style scoped>

</style>