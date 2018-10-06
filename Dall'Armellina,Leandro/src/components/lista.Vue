<template>
    <section>
        <h1>Hay persona/s agregadas: </h1>
            <article>
                <label for ="opcion_mostrar">Ver Personas agregadas segun sexo: </label>
                <select  id="opcion_mostrar">
                    <option value="Todos">Todos</option>
                    <option value="Masculino">Masculino</option>
                    <option value="Femenino">Femenino</option>
                    <option value="Otro">Otro</option>
                </select> 
                <ul v-if="personas.length">
                    <li v-for="p in personas" :key="p.id" >
                        Nombre: {{ p.nombre }} -- Edad :{{ p.edad }} -- Sexo: {{ p.sexo }}
                    <button  @click="eliminar">Remover</button>
                    </li>
                </ul> 
                <p v-else>No hay personas ingresadas!</p>
                </article>
    </section>
</template>

<script>
	export default {
        name: 'lista',
        props: ['personas'],
        methods: {
            eliminar() {
                this.$emit('eliminar');
            }
        }
        
    }
</script>
