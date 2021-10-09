<template>
  <table class="w-full text-md bg-white rounded mb4">
    <tbody>
      <tr class="border-b">
        <th class="text-left p-3 px-5">Descrição</th>
        <th class="text-left p-3 px-5">Data</th>
        <th class="text-left p-3 px-5">Concluída</th>
        <th></th>
      </tr>
      <tr
        v-for="(item, i) in tarefas"
        :key="item.descricao"
        :class="[
          { riscado: item.concluida },
          { 'bg-gray-100': i % 2 == 0 },
          'border-b hover:bg-gray-300',
        ]"
      >
        <td class="p-3 -px-5">{{ item.descricao }}</td>
        <td class="p-3 -px-5">{{ formatarData(item.data) }}</td>
        <td class="p-3 -px-5">
          <input v-model="item.concluida" type="checkbox" />
        </td>
      </tr>
    </tbody>
  </table>
</template>

<script>
import moment from "moment";
export default {
  props: ["tarefas"],
  methods: {
    formatarData(data) {
      return moment(data).format("DD/MM/yyyy");
    },
  },
};
</script>

<style>
.riscado {
  text-decoration: line-through crimson;
}
</style>
