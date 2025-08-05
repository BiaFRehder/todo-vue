<script setup>
    const props = defineProps(['tarefas']);
</script>

<template>
    <ul v-if="props.tarefas.length > 0" class="list-gorup mt-4">
        <li class="list-group-item" v-for="tarefa in props.tarefas">
            <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada"
                :id="tarefa.titulo" type="checkbox">
            <label :class="{ done: tarefa.finalizada === true }" class="ms-3" :for="tarefa.titulo">
                {{ tarefa.titulo }}
            </label>
        </li>
    </ul>
    <h4 class="mt-4" v-else>Não há tarefas pendentes.</h4>
</template>

<style scoped>
    .done {
        text-decoration: line-through;
    }
</style>