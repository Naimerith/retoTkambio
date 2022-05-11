<template>
  <div>
    <transition name="transition_Modal">
      <div class="modal" v-if="modal">
        <h1>Reporte por fecha de nacimiento</h1>
        <h3>Ingresa los siguientes datos para generar tu reporte</h3>
        <label for="">Descripción del reporte</label>
        <input type="text" /><br />
        <label for="">Fecha de nacimiento</label><br />
        <label for="">Inicio</label>
        <input type="date" />
        <label for="">Fin</label>
        <input type="date" />
        <div>
          <button @click="modal = false">Generar reporte</button>
        </div>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  name: "RegisterForms",
  data() {
    return {
      modal: false,
    };
  },
};
</script>

<style>
.modal {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background: #ffffff;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  border-radius: 10px;
}
</style>