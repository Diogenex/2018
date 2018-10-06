<template>
    <section>
        <h1>Registro de Personas: </h1>
        <label for="Nombre">Nombre: </label>
        <input type="text" id="Nombre" v-model="nombre">
        <label for="Edad">Edad: </label>
        <input type="number" min="1" max="123" id="Edad" v-model.number="edad">
        <label for="Sexo">Sexo: </label>
        <select id="Sexo" v-model="sexo">
            <option value="Masculino">Masculino</option>
            <option value="Femenino">Femenino</option>
            <option value="Otro">Otro</option>
        </select> 
        <button @click="agregar()">Agregar</button>
    </section>
</template>

<script>
	export default {
        name: 'formulario',
        data() {
            return {
                nombre : this.nombre,
                edad: this.edad,
                sexo: this.sexo 
            }
        },
        methods: {
            agregar() {
                if (isNaN(this.nombre) && this.edad !== "" && this.sexo !== "") {
                    this.$emit('agregar',this.nombre, this.edad, this.sexo);
                }else{
                    alert("Complete todos los campos del formulario");
                }
            }
        }
    }
</script>

