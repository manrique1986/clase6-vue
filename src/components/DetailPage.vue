<template>
     <div>
        <hr>
        <h1 class="display-2 text-center">Detalle</h1>
        <h3>Nombre: {{nombre}}</h3>
        <p>Descripción: {{}}</p>
        
    </div>
</template>

<script>
export default {
  name: "DetailPage",

  props: ["products"],
  data() {
    return {
    
    };
  },

};
</script>

<style scoped>

  







</style>