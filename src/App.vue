<template>
  <div id="app">
    <h3 class="titulo1">Cerveza Artesanal</h3>
    <br />
    <Products   v-for="(product, i) in products"
      :key="i"
      :id="product.id"
      :titulo="product.titulo"
      :precio="product.precio"
      :sabor="product.sabor"
      :imagen="product.imagen"
      />
  </div>
</template>

<script>
import Products from './components/Products.vue'

export default {
  name: 'App',
  components: {
    Products
  },
    data() {
    return {
      products: [
        {
          id: 1,
          titulo: "Honey",
          sabor: "Dulce",
          precio: 350,
          imagen:
            "https://res.cloudinary.com/dytpump6i/image/upload/v1653932402/honey_knvkxz.jpg",
        },
        {
          id: 2,
          titulo: "Blonde",
          sabor: "Amarga",
          precio: 400,
          imagen:
            "https://res.cloudinary.com/dytpump6i/image/upload/v1653932534/blonde2_ts180x.jpg",
        },
        {
          id: 3,
          titulo: "Ipa",
          sabor: "Amarga",
          precio: 400,
          imagen:
            "https://res.cloudinary.com/dytpump6i/image/upload/v1653932553/ipa_yf51hn.jpg",
        },
        {
          id: 4,
          titulo: "Scottish",
          sabor: "Dulce",
          precio: 350,
          imagen:
            "https://res.cloudinary.com/dytpump6i/image/upload/v1653932564/scottish_izjelm.jpg",
        },
      ],
    productosEnCarrito: [],
    };
  },
}
</script>

<style>

.titulo1 {
  text-align: center;
  color: brown;
}

</style>
