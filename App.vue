<template>
  <div>
    <div v-for="resultado in resultados" :key="resultado.id">
      <p>- Nombre: {{ resultado.nombre }}</p>
      <p>- Apellidos: {{ resultado.apellidos }}</p>
      <p>- Dirección: {{ resultado.direccion }}</p>
      <p>- Teléfono: {{ resultado.telefono }}</p>
      <p>- Edad: {{ resultado.edad }}</p>
    </div>
    <div v-if="!resultados || resultados.length === 0">
      <p>No hay más datos.</p>
    </div>
  </div>
</template>

<script>
import connection from './db.js';

export default {
  data() {
    return {
      resultados: null
    };
  },
  mounted() {
    connection.query('SELECT * FROM agenda2', (error, results) => {
      if (error) {
        console.error(error);
      } else {
        this.resultados = results;
      }
    });
  }
};
</script>
