<template>
  <table border="1">
    <thead>
      <th>Descrição</th>
      <th>Data</th>
      <th>Concluida</th>
    </thead>
    <tbody>
      <tr
        v-for="item in tarefas"
        :key="item.descricao"
        :class="{ riscado: item.concluida }"
      >
        <td>{{ item.descricao }}</td>
        <td>{{ formatarData(item.data) }}</td>
        <td>
          <input v-model="item.concluida" type="checkbox" />
        </td>
      </tr>
    </tbody>
  </table>
</template>

<script>
import moment from 'moment'
export default {
    props:["tarefas"],
    methods: {
        formatarData(data) {
            return moment(data).format("DD/MM/yyyy")
        }
    }

}
</script>

<style>
.riscado {
  text-decoration: line-through crimson;
  
}
</style>