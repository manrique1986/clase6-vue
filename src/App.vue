<template>
  <div id="app">
    <BarraNav />
    <h3 class="titulo1">Cerveza Artesanal</h3>
    <br />

    <div v-if="!canAccess">
      <button class="buttonLogin" data-mdb-toggle="pill" @click="cambiardeRutaLogin" role="tab"
        aria-controls="pills-login" aria-selected="true">
        Login/register
      </button>
      <LoginPage v-show="estoyEnLogin" @changeFlag="recibiElMensaje" />
    </div>
    <div v-if="!canAccess">
      <RegisterPage v-show="!estoyEnLogin" @enviarRegistro="recibirRegistro" />
    </div>

    <div v-else>
      <Products v-for="(product, i) in products" :key="i" :id="product.id" :titulo="product.titulo"
        :precio="product.precio" :sabor="product.sabor" :imagen="product.imagen" :detail="product.detail" />
    </div>
    <DetailPage />
  </div>
</template>

<script>
import Products from "./components/Products.vue";
import BarraNav from "./components/BarraNav.vue";
import LoginPage from "./components/LoginPage.vue";
import DetailPage from "./components/DetailPage.vue";
import RegisterPage from "./components/RegisterPage.vue";

export default {
  name: "App",
  components: {
    Products,
    BarraNav,
    LoginPage,
    DetailPage,
    RegisterPage

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

          detail: "Las cervezas Honey se elaboran con miel, la que les aporta a un sabor dulce y azúcares  fermentables que elevan el contenido alcohólico de la cerveza."

        },
        {
          id: 2,
          titulo: "Blonde",
          sabor: "Amarga",
          precio: 400,
          imagen:
            "https://res.cloudinary.com/dytpump6i/image/upload/v1653932534/blonde2_ts180x.jpg",

          detail: "Tienen un cuerpo ligero, poco amargor y aroma a lúpulo y algunos toques  dulces  (debido a la malta)."
        },
        {
          id: 3,
          titulo: "Ipa",
          sabor: "Amarga",
          precio: 400,
          imagen:
            "https://res.cloudinary.com/dytpump6i/image/upload/v1653932553/ipa_yf51hn.jpg",

          detail: "En una IPA encontramos un prominente a intenso aroma a lúpulo, ya sean cítricos, florales, pináceos, resinosos, especiados, a frutas, etc."

        },
        {
          id: 4,
          titulo: "Scottish",
          sabor: "Dulce",
          precio: 350,
          imagen:
            "https://res.cloudinary.com/dytpump6i/image/upload/v1653932564/scottish_izjelm.jpg",

          detail: " Quizás la más definida de sus características que diferencian a las cervezas de Escocia de otras oscuras es su sabor limpio, fresco."

        },
      ],
      canAccess: false,
      estoyEnLogin: true,
      listadoDeUsuarios: [],
    };
  },

  methods: {
    recibiElMensaje() {
      this.canAccess = !this.canAccess;
    },

    recibirRegistro(payload) {
      this.listadoDeUsuarios.push(payload);
    },

    cambiardeRutaLogin() {
      this.estoyEnLogin = !this.estoyEnLogin;
    },
  },
};
</script>

<style>
.titulo1 {
  text-align: center;
  color: brown;
}

.buttonLogin {
  margin-left: 25px;
  border-radius: 10px;
}

.buttonLogin:hover {
  background-color: brown;
  color: white;
}
</style>
