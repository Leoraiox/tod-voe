<script setup>
    const props = defineProps(['tarefas']);
</script>

<template>
    <!-- Se houver tarefas, renderiza a lista -->
    <ul v-if="props.tarefas.length > 0" class="list-group mt-4">
    <li class="list-group-item" v-for="tarefa in props.tarefas" :key="tarefa.titulo">
        <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada" :id="tarefa.titulo" type="checkbox">
        <label :class="{ done: tarefa.finalizada }" class="ms-3" :for="tarefa.titulo">
        {{ tarefa.titulo }}
        </label>
    </li>
    </ul>

    <!-- Se não houver tarefas, mostra essa mensagem -->
    <p v-else class="mt-4 text-muted">Não existem tarefas pendentes.</p>
</template>

<style scoped>

    .done {
        text-decoration: line-through;
    }
</style>