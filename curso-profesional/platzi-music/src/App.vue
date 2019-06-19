<template>
  <div class="container">
    <div id="formLogin" class="login">
      <img src="./assets/img-logo.jpg">
      <h1 class="login-form_title">{{title}}</h1>
      <form action class="form">
        <label for class="form__label">{{ labelName }}</label>
        <input type="text" class="form__input">
        <label for class="form__label">{{ labelSubname }}</label>
        <input type="text" class="form__input">
        <label for class="form__label">{{ labelCargo }}</label>
        <input type="text" class="form__input">
        <input type="submit" :value="send | uppercase" class="form__button">
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "formLogin",

  data() {
    return {
      title: "Registro estación Platzi",
      labelName: "Nombre",
      labelSubname: "Apellido",
      labelCargo: "Cargo",
      send: "Enviar"
    };
    data: {
      datos: [];
    }
  },
  filters: {
    uppercase: function(str) {
      return str.toUpperCase();
    }
  },
  methods: {}
};
</script>

<style lang="scss">
@import "./scss/main.scss";
</style>
