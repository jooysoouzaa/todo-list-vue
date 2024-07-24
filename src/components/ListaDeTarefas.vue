<script setup>
const props = defineProps(['tarefas'])
</script>

<template>
    <div>
        <div v-if="props.tarefas.length > 0">
            <ul class="list-group mt-4">
                <li class="list-group-item bg-dark text-light border-0" v-for="tarefa in props.tarefas" :key="tarefa.titulo">
                    <div class="d-flex align-items-center">
                        <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada"
                            :id="tarefa.titulo" type="checkbox" class="custom-checkbox">
                        <label :class="{ done: tarefa.finalizada }" class="ms-3 mb-2" :for="tarefa.titulo">
                            {{ tarefa.titulo }}
                        </label>
                    </div>
                </li>
            </ul>
        </div>
        <div v-else>
            <p class="mt-4">Não existem tarefas pendentes</p>
        </div>
    </div>
</template>

<style scoped>
li {
    padding: 0;
    background-color: none;
}

.done {
    text-decoration: line-through;
}

.custom-checkbox {
    appearance: none; /* Remove o estilo padrão */
    width: 1.2em;
    height: 1.25em;
    border: none;
    border-radius: 0.2em;
    background-color: #121213;
    cursor: pointer;
    position: relative;
}

.custom-checkbox:checked {
    background-color: #c00070;
    border-color: #c00070;
}

.custom-checkbox:checked::after {
    content: '';
    position: absolute;
    top: 0.1em;
    left: 0.4em;
    width: 0.5em;
    height: 0.8em;
    border: solid #fff;
    border-width: 0 0.2em 0.2em 0;
    transform: rotate(45deg);
}

</style>
