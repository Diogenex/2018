<template>
  <div id="app">
    <formulario @agregar="agregar"></formulario>
    <lista :personas="personas"></lista>            
  </div>   
</template>

<script>
import formulario from './components/formulario.vue';
import lista from './components/lista.vue';


export default {
	name: 'app',
	components: {
    formulario,
    lista
  },
	data() {
		return {
			personas: [],
      persona: 
      {
        nombre: "",
        edad: "",
        sexo: ""
      }
		}
	},
	methods: {
    agregar(nombre,edad,sexo) {
      this.personas.push({
        nombre: nombre,
        edad: edad,
        sexo: sexo
      });
    }
	}
}
</script>
