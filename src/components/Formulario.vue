<script setup>
const props = defineProps(['cadastraTarefa', 'tarefaTemp', 'trocarFiltro', 'editaTarefaTemp'])
</script>

<template>
    <form @submit.prevent="props.cadastraTarefa">
        <div class="row">
            <div class="col">
                <input :value="props.tarefaTemp" @change="props.editaTarefaTemp" required type="text"
                    placeholder="Digite aqui a descrição da tarefa" class="form-control">
            </div>
        </div>
        <div class="row">
            <div class="col-7 mt-2">
                <button type="submit" class="btn btn-primary custom-button">Cadastrar tarefa</button>
            </div>
            <div class="col-5 mt-2 position-relative">
                <i class="bi bi-funnel position-absolute top-50 ps-2 pe-3 translate-middle-y "></i>
                <select @change="props.trocarFiltro" class="form-control select">
                    <option value="" disabled selected hidden>Filtre tarefas..</option>
                    <option value="todas">Todas as tarefas</option>
                    <option value="pendentes">Pendentes</option>
                    <option value="finalizadas">Finalizadas</option>
                </select>
            </div>
        </div>
    </form>
</template>

<style scoped>

.select{
    padding-left: 30px;
}
input {
    background-color: #121213;
    border: none;
    color: #fff;
}

select {
    background-color: #1212139a;
    border: none;
    color: #fff;
}

select:focus {
    background-color: #121213;
    color: #fff;
    border-color: #c00070;
    outline: none;
    box-shadow: 0 0 0 3px rgba(192, 0, 112, 0.5);
}

input::placeholder {
    color: #666666;
}

input:focus {
    background-color: #121213;
    color: #fff;
    border-color: #c00070;
    outline: none;
    box-shadow: 0 0 0 3px rgba(192, 0, 112, 0.5);
}

button {
    background-color: #c00070 !important;
    border: none;
}

button:hover {
    background-color: #a50060 !important;
}

button:active {
    background-color: #c00070 !important;
}

button:focus {
    background-color: #c00070 !important;
    box-shadow: none;
}
</style>
