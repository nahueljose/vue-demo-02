<template>
  <div class="contenedor-tareas">
    <ol>
      <li
        v-for="tarea in tareas"
        v-bind:key="tarea.id"
        v-bind:class="{completada: tarea.completada}"
        @click="tareaClick(tarea.id)"
      >
        {{ tarea.label }}
      </li>
    </ol>
  </div>
</template>

<script>
export default {
  name: "ListaTareas",
  props: {
    tareas: Array
  },
  methods: {
    tareaClick(idTarea) {
      this.$emit('click-tarea', idTarea);
    }
  }
}
</script>

<style scoped>
.completada {
  text-decoration:line-through;
  opacity: 0.5;
}
</style>