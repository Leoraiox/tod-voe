<script setup>
const props = defineProps(['cadastraTarefa', 'tarefaTemp', 'trocarFiltro','editaTarefaTemp']);

</script>

<template>
    <form @submit.prevent="props.cadastraTarefa">
        <div class="row">
            <div class="col">
                <input :value="props.tarefaTemp" @change="props.editaTarefaTemp" required 
                type="text" placeholder="Digite uma nova tarefa" class="form-control">
            </div>
        <div class="col-md-2">
            <button type="submit" class="btn btn-primary">Cadastrar</button>
        </div>
            <div class="col-md-2">
                <select @change="props.trocarFiltro" class="form-control">
                    <option value="todas">Todas tarefas</option>
                    <option value="finalizadas">Tarefas finalizadas</option>
                    <option value="pendentes">Tarefas pendentes</option>
                </select>
            </div>
        </div>
    </form>
</template>