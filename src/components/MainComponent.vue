<template>
  <div class="container_template">
    <header class="container_header">
      <h1 class="text_header">tk<span class="text_header2">ambío</span></h1>
    </header>
    <h2 class="title_app">Generador de reportes TK</h2>
    <div>
      <table class="table_Reports">
        <thead>
          <tr>
            <th>Titulo</th>
            <th>Fecha de creación</th>
            <th>Acción</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="lists of list" v-bind:key="lists">
            <td>{{ lists.description }}</td>
            <td>{{ lists.startDate }}</td>
            <td>Descargar ⇩</td>
          </tr>
        </tbody>
      </table>
    </div>

    <div class="modal" v-if="modal">
      <form action="" v-on:submit.prevent="generate()">
        <h1 class="title_modal">Reporte por fecha de nacimiento</h1>
        <h3 class="subtitle_modal">
          Ingresa los siguientes datos para generar tu reporte
        </h3>
        <div class="description_reports">
          <p class="text_description">Descripción del reporte</p>
          <input type="text" v-model="description" /><br />
        </div>
        <p class="text_birthdat">Fecha de nacimiento</p>
        <div class="container_date">
          <div class="date">
            <p class="text_date">Inicio</p>
            <input type="date" v-model="startDate" />
          </div>
          <div class="date">
            <p class="text_date">Fin</p>
            <input type="date" v-model="endDate" />
          </div>
        </div>
        <div class="container-btnModal">
          <button class="btn_modal" type="submit">Generar reporte</button>
        </div>
      </form>
    </div>

    <button class="btn" @click="modal = true">Crear reporte</button>
  </div>
</template>

<script>
export default {
  name: "MainComponent",

  data() {
    return {
      modal: false,
      description: "",
      startDate: "",
      endDate: "",
      list: [],
    };
  },
  created: function () {
    this.iniziateList();
  },
  methods: {
    iniziateList() {
      let data = localStorage.getItem("addRegisters");
      if (data != null) {
        this.list = JSON.parse(data);
      }
    },
    generate() {
      const registers = {
        description: this.description,
        startDate: this.startDate,
        endDate: this.endDate,
      };

      let arraySaved = localStorage.getItem("addRegisters");
      let arrayTemp = [];

      if (arraySaved != null) {
        arrayTemp = JSON.parse(arraySaved);
      }

      arrayTemp.push(registers);
      localStorage.setItem("addRegisters", JSON.stringify(arrayTemp));
      this.description = "";
      this.startDate = "";
      this.endDate = "";
      this.modal = false;
      this.list = arrayTemp;
    },
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
  height: 90px;
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
  width: 15%;
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
  box-shadow: 0px 8px 8px rgba(0, 0, 0, 0.25);
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 30px 10px 20px;
  width: 450px;
  height: 350px;
}
.title_modal {
  font-family: "Argentum Sans";
  font-style: normal;
  font-weight: 800;
  font-size: 24px;
  line-height: 28px;
  display: flex;
  align-items: center;
  text-align: center;
  justify-content: space-around;
  color: #181818;
  padding: 10px;
}
.subtitle_modal {
  font-family: "Argentum Sans";
  font-style: normal;
  font-weight: 100;
  font-size: 16px;
  line-height: 16px;
  display: flex;
  align-items: center;
  text-align: center;
  color: #9b9090;
  padding: 10px;
}
input {
  height: 54px;
  border: 1px solid rgba(0, 0, 0, 0.12);
  border-radius: 6px;
  font-family: "Argentum Sans";
  font-style: normal;
  font-weight: 300;
  font-size: 12px;
  line-height: 16px;
  color: #9b9090;
  letter-spacing: 0.2px;
}
.description_reports,
.date {
  margin-top: 5%;
  display: flex;
  flex-direction: column;
  align-items: stretch;
  align-content: stretch;
}
.container_date {
  display: flex;
  justify-content: space-between;
}
.date {
  width: 47%;
}
.text_birthdat {
  font-family: "Argentum Sans";
  font-style: normal;
  font-weight: 300;
  font-size: 12px;
  line-height: 16px;
  color: #9b9090;
  letter-spacing: 0.2px;
}
.text_description,
.text_date {
  font-family: "Argentum Sans";
  font-style: normal;
  font-weight: 300;
  font-size: 12px;
  line-height: 16px;
  color: #9b9090;
  letter-spacing: 0.2px;
  position: absolute;
  margin: -9px 0 0 13px;
  background: #ffffff;
}
.container-btnModal {
  display: flex;
  justify-content: center;
  align-items: center;
}
.btn_modal {
  padding: 16px 50px;
  width: 200px;
  height: 51px;
  background: #cfcfcf;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  border-radius: 50px;
  border: none;
  cursor: pointer;
  margin-top: 4%;
  font-family: "Argentum Sans";
  font-size: 12px;
}
.table_Reports {
  width: 690px;
  height: 212px;
  background: #4563e6;
  border-radius: 10px;
  color: #ffffff;
  margin: 5% 0;
}
th {
  font-family: "Argentum Sans";
  font-weight: lighter;
  font-size: 18px;
  line-height: 24px;
  letter-spacing: 0.15px;
  color: #ffffff;
  justify-content: center;
}
td {
  font-family: "Argentum Sans";
  font-weight: lighter;
  font-size: 14px;
  line-height: 14px;
}
tr {
  display: flex;
  margin: 1%;
  justify-content: space-around;
  align-items: center;
}
</style>
