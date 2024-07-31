<template>
    <div class="d-flex justify-content-evenly gap-2 p-2">
        <div id="cita" class="card w-100" style="max-width: 18rem;" :style="{background: colorFondo}">
            <div id="paciente" class="card-body"  >
                <h2 class="card-title fs-6">Paciente</h2>
                <p class="card-text">{{ nuevoPaciente }}</p>
                <h2 class="card-title fs-6">Fecha</h2>
                <p class="card-text">{{ nuevaFecha }}</p>
                <h2 class="card-title fs-6">Hora</h2>
                <p class="card-text">{{ nuevaHora }}</p>
                <h2 class="card-title fs-6">Motivo</h2>
                <p class="card-text">{{ nuevoMotivo }}</p>
                <button class="btn btn-secondary" @click="$emit('eliminarCita')" >Eliminar</button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'CardRegistro',
    data(){
        return {           
            colorFondo: 'red',
        }
    },
    props: ["nuevoPaciente", "nuevaFecha", "nuevaHora", "nuevoMotivo", "gravedades"],
    
}

</script>

<style scoped>


</style>