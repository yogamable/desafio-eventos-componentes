<template>
  <div>
    <h1 class="d-flex justify-content-center pt-4">Registro de Citas Médicas</h1>
    
    <div class="border border-2 rounded-4 m-4 p-4">
      <form class="d-flex justify-content-center gap-1">
        <div>
          <label :class="{'text-black': nuevoPaciente}" class="form-label text-danger" for="paciente">Paciente</label>
          <input v-model="nuevoPaciente" class="form-control" type="text" name="paciente" id="paciente" />
        </div>
        <div>
          <label :class="{'text-black': nuevaFecha}" class="form-label text-danger" for="fecha" >Fecha</label>
          <input v-model="nuevaFecha" class="form-control" type="date" name="fecha" id="fecha" />
        </div>
        <div>
          <label :class="{'text-black': nuevaHora}" class="form-label text-danger" for="hora" >Hora</label>
          <input v-model="nuevaHora" class="form-control" type="time" name="hora" id="hora" />
        </div>
        <div>
          <label :class="{'text-black': gravedadElegida}" class="form-label text-danger" for="gravedad" >Gravedad</label>
          <select class="form-control" name="gravedad" id="gravedad" v-model="gravedadElegida">
            <option v-for="gravedad in gravedades" :key="gravedad" :value="gravedad"> {{ gravedad }}</option>
          </select>
        </div>
        <div>
          <label :class="{'text-black': nuevoMotivo}" class="form-label text-danger" for="motivo" >Motivo</label>
          <input v-model="nuevoMotivo" class="form-control" type="text" name="motivo" id="motivo" />
        </div>
      </form>
      <div class="d-flex justify-content-center mt-3">
        <button class="btn btn-primary" type="submit" @click="agregarCita" >Agregar</button>
      </div>
      <p class="text-danger text-center pt-4" :style="{display: mensajeConsultas}" >Aún no hay consultas registradas</p>
    </div>

  </div>
</template>

<script>
export default {
  name: 'RegistroCitas',
  
  data(){
    return {
      nuevoPaciente: '',
      nuevaFecha: '',
      nuevaHora: '',
      gravedades: ["Baja", "Media", "Alta"],      
      nuevoMotivo: '',
      gravedadElegida: '',
      mensajeConsultas: '',
      color: '',
    }
  },
  methods: {
    agregarCita(){
      const nuevoPaciente = this.nuevoPaciente;
      const nuevaFecha = this.nuevaFecha;
      const nuevaHora = this.nuevaHora;
      const nuevoMotivo = this.nuevoMotivo;
      const gravedadElegida = this.gravedadElegida;
      const color = this.color;

      this.$emit('agregarCita', {
        nuevoPaciente,
        nuevaFecha,
        nuevaHora,
        nuevoMotivo,
        gravedadElegida,
        color,
      });
    },
    
  },
  
}
</script>

<style scoped>
  .text-black{
    color: black;
  }
</style>
