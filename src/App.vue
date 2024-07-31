<template>
  <div id="app">
    <div>
      <RegistroCitas 
        @agregarCita="(cita)=>this.citas.push(cita)"
      />
      
    <section v-for="(cita, index) in citas" :key="cita">
      <CardRegistro
        :nuevoPaciente = "cita.nuevoPaciente"
        :nuevaFecha = "cita.nuevaFecha"
        :nuevaHora = "cita.nuevaHora"
        :nuevoMotivo = "cita.nuevoMotivo"
        :gravedades = "cita.gravedades"
        
        @eliminarCita="citas.splice(index,1)"
      />   
    </section>
    </div>
  </div>
</template>

<script>
import RegistroCitas from './components/RegistroCitas.vue';
import CardRegistro from './components/CardRegistro.vue';

export default {
  name: 'App',
  
  data(){
    return {
      citas: [],
    };
  },
  components: {
    RegistroCitas,
    CardRegistro,
  },
  
}
</script>

<style>

</style>
