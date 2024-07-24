<script setup>
    const props = defineProps(['tarefasPendentes'])
</script>
<template>
    <header class=" text-center p-3 mb-4 mt-4  rounded-3">
        <h1>Minhas tarefas</h1>
        <p>
        Você possui {{ props.tarefasPendentes }} tarefas pendentes
        </p>
    </header>
    </template>

<style>
header{
    background-color: #c00070;
}

</style>
