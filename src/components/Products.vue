<template>
  <div class="product">
    <div class="productos">
      <div class="card" style="width: 18rem">
        <h5 class="card-title text-center">{{ titulo }}</h5>
        <img class="img-card" :src="imagen" alt="" />
        <!-- <img :src="getImgUrl()" class="card-img-top d-block w-50" :alt="titulo"> -->
        <div class="card-body">
          <p class="card-text">${{ precio }}</p>
          <button class="btn btn-success text-center">Agregar</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    titulo: {
      type: String,
      required: true,
    },
    precio: {
      type: Number,
      required: true,
    },
    id: {
      type: Number,
      required: true,
    },
    sabor: {
      type: String,
      required: true,
    },
    imagen: {
      type: String,
      required: true,
    },
    products: {
      type: Array,
      required: true,
    },
  },
};
</script>


<style scoped>

.productos {
  text-align: center;
  padding: 15px;
  margin: auto;
  border-radius: 10px;
  box-shadow: 1px 4px 10px 0 brown;
  float: right;
}
.img-card {
  width: 150px;
  height: 150px;
}


.product{

  margin: 75px;
}
</style>
