<template>
  <h1>{{ titulo }}</h1>
  <br />
  <label for="descricao">Descrição:</label>
  <input
    v-model="tarefa.descricao"
    id="descricao"
    type="text"
    placeholder="Digite a descrição da tarefa"
  />
  <br />
  <label for="data">Data:</label>
  <input v-model="tarefa.data" id="data" type="date" />
  <br />
  <button @click="salvar">Salvar</button>
  <br />

  <TabelaTarefas :tarefas="tarefas"></TabelaTarefas>
  
</template>

<script>
import TabelaTarefas from './components/TabelaTarefas.vue'
export default {
  components: {
    TabelaTarefas
  },
  data() {
    return {
      titulo: "Todolist Vite",
      tarefa: {},
      tarefas: [],
    };
  },
  methods: {
    salvar() {
      this.tarefas.push(Object.assign({}, this.tarefa)); // deep copy
    },
  },
};
</script>

<style>

</style>
