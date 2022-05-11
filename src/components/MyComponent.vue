<template>
  <div class="container_template">
    <header class="container_header">
      <h1 class="text_header">tk<span class="text_header2">ambío</span></h1>
    </header>
    <h2 class="title_app">Generador de reportes TK</h2>
    <div>aqui v la tbla</div>

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

    <button class="btn" @click="modal = true">Crear reporte</button>
  </div>
</template>

<script>
export default {
  name: "MyComponent",
  data() {
    return {
      modal: false,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Open+Sans:wght@800&display=swap");
@import url(//db.onlinewebfonts.com/c/203f1615b37d6fb2fcd85695bc4c4b00?family=Argentum+Sans);
* {
  margin: 0;
  padding: 0;
}
.container_template {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.container_header {
  height: 70px;
  width: 100vw;
  background: linear-gradient(
    180deg,
    #02adf1 -2.37%,
    #4562e6 124.84%,
    #4563e6 124.84%
  );
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
}
.text_header {
  display: flex;
  justify-content: center;
  color: #f2b705;
  font-family: "Open Sans", sans-serif;
}
.text_header2 {
  color: #fbffff;
  font-family: "Open Sans", sans-serif;
}
.title_app {
  display: flex;
  justify-content: center;
  margin-top: 5%;
  font-family: "Argentum Sans";
  font-style: normal;
  font-weight: 300;
  line-height: 33px;
}
.btn {
  background: #ffbe12;
  border: none;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  border-radius: 50px;
  font-family: "Argentum Sans";
  font-size: 14px;
  padding: 10px;
  cursor: pointer;
}
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
