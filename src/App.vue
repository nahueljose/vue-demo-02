<template>
  <div>
    <h1>Mi lista de tareas</h1>

    <NuevaTarea @nueva-tarea="guardarTarea" />
    <ListaTareas @click-tarea="completarTarea" :tareas="tareas" />
  </div>
</template>

<script>
import NuevaTarea from './components/NuevaTarea.vue';
import ListaTareas from './components/ListaTareas.vue';

export default {
  name: 'App',
  components: {
    NuevaTarea,
    ListaTareas
  },
  data: function() {
    return {
      tareas: []
    }
  },
  methods: {
    /**
     * Guardar tareas
     */
    guardarTarea(texto){
      this.tareas.push({
        id: Math.random(),
        label: texto,
        completada: false
      });
    },
    /**
     * Método para completar tareas
     */
    completarTarea(idTarea) {
      this.tareas.forEach(tarea => {
        if (idTarea === tarea.id) {
          tarea.completada = !tarea.completada
        }
      })
    }
  }
}
</script>

<style>

</style>
