<template>
  <div id="app">
    <div>
      <RegistroCitas 
        @agregarCita="recibirDatos"
      />
      
      <section class="d-flex row gap-2 p-4" >
        <CardRegistro v-for="(cita, index) in citas" 
          :key="index" 
          :cita = "cita"
          :style="{backgroundColor: cita.color}"
          
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
  methods: {
    recibirDatos(cita){
      console.log(cita);
      cita.color = this.obtenerColor(cita.gravedadElegida);
      this.citas.push(cita);
    },
    obtenerColor(gravedad){
      if (gravedad === 'baja') {
        return 'green';
      } else if (gravedad === 'media') {
        return 'yellow';
      } else if (gravedad === 'alta') {
        return 'red';
      } else{
        return 'white';
      }
    },
  }, 
  
}
</script>

<style>

</style>
