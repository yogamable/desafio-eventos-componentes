<template>
    
    <div id="cita" class="card w-100" style="max-width: 18rem;" >
        <div id="paciente" class="card-body"  >
            <h2 class="card-title fs-6">Paciente</h2>
            <p class="card-text">{{ cita.nuevoPaciente }}</p>
            <h2 class="card-title fs-6">Fecha</h2>
            <p class="card-text">{{ cita.nuevaFecha }}</p>
            <h2 class="card-title fs-6">Hora</h2>
            <p class="card-text">{{ cita.nuevaHora }}</p>
            <h2 class="card-title fs-6">Motivo</h2>
            <p class="card-text">{{ cita.nuevoMotivo }}</p>
            <button class="btn btn-secondary" @click="this.$emit('eliminarCita')" >Eliminar</button>
        </div>
    </div>
   
</template>

<script>
export default {
    name: 'CardRegistro',
    data(){
        return {           
            
        }
    },
    props: {cita: Object},
    
}

</script>

<style scoped>


</style>