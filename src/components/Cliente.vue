<template>
  <tr>
    <th>{{ cliente.nome }}</th>
    <td>{{ cliente.email }}</td>
    <td>{{ cliente.idade }}</td>
  </tr>
</template>

<script>
export default {
  data() {
    return {};
  },
  props: {
    cliente: Object,
  },
};
</script>

<style>
</style>