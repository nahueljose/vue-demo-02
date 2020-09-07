<template>
  <div>
    <input type="text" v-model="label" />
    <button @click="agregarTarea">Agregar tarea</button>
  </div>
</template>

<script>
export default {
  name: "NuevaTarea",
  data: function(){
    return {
      label: ""
    }
  },
  methods: {
    /**
     * Agrega una tarea nueva
     */
    agregarTarea(){
      if( this.label !== "" ) {
        this.$emit('nueva-tarea', this.label);
        this.label = ""
      }
    }
  }
}
</script>