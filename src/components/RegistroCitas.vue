<template>
  <div>
    <h1 class="d-flex justify-content-center pt-4">Registro de Citas Médicas</h1>
    
    <div class="border border-2 rounded-4 m-4 p-4">
      <form class="d-flex justify-content-center gap-1">
        <div>
          <label class="form-label" for="paciente">Paciente</label>
          <input v-model="nuevoPaciente" class="form-control" type="text" name="paciente" id="paciente" />
        </div>
        <div>
          <label class="form-label" for="fecha" >Fecha</label>
          <input v-model="nuevaFecha" class="form-control" type="date" name="fecha" id="fecha" />
        </div>
        <div>
          <label class="form-label" for="hora" >Hora</label>
          <input v-model="nuevaHora" class="form-control" type="time" name="hora" id="hora" />
        </div>
        <div>
          <label class="form-label" for="gravedad" >Gravedad</label>
          <select class="form-control" name="gravedad" id="gravedad">
            <option v-for="gravedad in gravedades" :key="gravedad"> {{ gravedad }}</option>
          </select>
        </div>
        <div>
          <label class="form-label" for="motivo" >Motivo</label>
          <input v-model="nuevoMotivo" class="form-control" type="text" name="motivo" id="motivo" />
        </div>
      </form>
      <div class="d-flex justify-content-center mt-3">
        <button class="btn btn-primary" type="submit" @click="$emit(agregarCita(cita))" >Agregar</button>
      </div>
      <p class="text-danger text-center pt-4" v-if="mostrarMensaje">Aún no hay consultas registradas</p>
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
        mostrarMensaje: '',
    }
  },
  methods: {
    agregarCita(){
      const nuevoPaciente = this.nuevoPaciente;
      this.pacientes.push(nuevoPaciente);
      this.nuevoPaciente = "";

      const nuevaFecha = this.nuevaFecha;
      this.nuevaFecha.push(nuevaFecha);
      this.nuevoPaciente = "";

      const nuevaHora = this.nuevaHora;
      this.nuevaHora.push(nuevaHora);
      this.nuevaHora = "";

      const nuevoMotivo = this.nuevoMotivo;
      this.nuevoMotivo.push(nuevoMotivo);
      this.nuevoMotivo = "";
    },
  },
  
}
</script>

<style scoped>

</style>
