<template>
  <h1 class="text-6xl text-center mt-28">{{ titulo }}</h1>
  <div
    class="
      space-y-4
      border-2 border-gray-300
      w-1/3
      rounded-sm
      p-8
      mx-auto
      mt-20
      
    "
  >
    <div>
      <label for="descricao" class="bolck">Descrição:</label>
      <input
        v-model="tarefa.descricao"
        id="descricao"
        type="text"
        placeholder="Digite a descrição da tarefa"
        class="
          border-2 border-gray-300
          outline-none
          rounded-sm
          px-4
          py-1
          focus:border-blue-600
          w-full
        "
      />
    </div>
    <div>
      <label for="data" class="block">Data:</label>
      <input
        v-model="tarefa.data"
        id="data"
        type="date"
        class="
          border-2 border-gray-300
          outline-none
          rounded-sm
          px-4
          py-1
          focus:border-blue-600
          w-full
        "
      />
    </div>

    <app-btn class="mx-auto" @click="salvar">Salvar</app-btn>
  </div>

  <TabelaTarefas :tarefas="tarefas"></TabelaTarefas>
</template>

<script>
import TabelaTarefas from "./components/TabelaTarefas.vue";
import AppBtn from "./components/AppBtn.vue";
export default {
  components: {
    TabelaTarefas,
    AppBtn,
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

<style></style>
