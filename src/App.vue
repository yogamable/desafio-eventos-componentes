<template>
  <div id="app">
    <div>
      <RegistroCitas 
        @agregarCita="recibirDatos"
      />
      
      <section class="d-flex gap-2" >
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
      cita.color = this.obtenerColor(this.gravedadElegida);
      this.citas.push(cita);
    },
    obtenerColor(){
      if (this.gravedadElegida === 'baja') {
        this.color = 'green';
      } else if (this.gravedadElegida === 'media') {
        return 'yellow';
      } else if (this.gravedadElegida === 'alta') {
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
