<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <Agenda :contactos="contactoAgenda" />
  </div>
</template>

<script>
import Agenda from "./components/Agenda.vue";

export default {
  name: "App",
  data(){
    return {
      contactoAgenda :{
        id:1,
        nome : "Paulo Lopes Estevão",
        numero: 937868133,
        operadora : "unitel"

      }
    }
  },
  components: {
    Agenda,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
