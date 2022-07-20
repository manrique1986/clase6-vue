<template>
  <div class="form">
    <b-form  class="formulario">
      <label class="sr-only" for="inline-form-input-name">Usuario</label>
      <b-form-input
        v-model="usuario"
        id="inline-form-input-name"
        class="mb-2 mr-sm-2 mb-sm-0"
        placeholder="Usuario"
      ></b-form-input>

      <label class="sr-only" for="inline-form-input-username">Password</label>
      <b-input-group class="mb-2 mr-sm-2 mb-sm-0">
        <b-form-input
          v-model="password"
          id="inline-form-input-username"
          placeholder="password"
        ></b-form-input>
      </b-input-group>
      <label class="sr-only" for="inline-form-input-username">Mail</label>
      <b-input-group class="mb-2 mr-sm-2 mb-sm-0">
        <b-form-input
          v-model="mail"
          id="inline-form-input-username"
          placeholder="mail"
        ></b-form-input>
      </b-input-group>

      <b-button @click="cambiarValor" variant="primary">Login</b-button>
    </b-form>
  </div>
</template>

<script>
export default {
  name: "RegistePage",
  data() {
    return {
      usuario: "",
      password: "",
      mail:"",
    };
  },
  methods: {
    cambiarValor() {
      if (this.usuario == "administrador" && this.password == "1234") {
        this.$emit("changeFlag");
      }
    },
  },
};
</script>

<style scoped>
.formulario {
  text-align: center;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    width: 300px;
    height: 150px;
    margin-left: 550px;
    margin-top: 150px;
  
}






</style>