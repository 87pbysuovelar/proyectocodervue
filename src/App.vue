<template>
  <div id="app">
    <Header />
    <main>
      <section id="main">
        <img src="img/portada.jpg" class="img-fluid" alt="..." width="100%">
      </section>

      <!-- productos -->
      <section id="productos">
        <div class="small-container" id="productos" style="position: relative;">
          <h2 class="title">Productos</h2>
          <div class="row" id="productos2">
            <div v-for="product in stockData" :key="product.id" class="col-md-4">
              <h3>{{ product.nombre }}</h3>
              <img :src="product.imagen" alt="Imagen del producto" class="img-fluid">
              <p>{{ product.descripcion }}</p>
              <p>Precio: {{ product.precio }}</p>
              <!-- Agrega aquí cualquier otro contenido relacionado con el producto -->
            </div>
          </div>
          <div class="carrito" id="carrito">
            <div class="header-carrito">
              <h2>Tu Carrito</h2>
            </div>
            <div class="carrito-items" id="carrito-items"></div>
            <div class="carrito-total">
              <div class="fila">
                <strong>Tu Total</strong>
                <span class="carrito-precio-total" id="carrito-precio-total"></span>
              </div>
              <button class="btn-pagar" onclick="confirmarCompra()">Pagar <i class="fa-solid fa-bag-shopping"></i></button>
            </div>
          </div>
        </div>
      </section>

      <!-- fan marolio registro-->
      <section id="fan">
        <section class="">
          <h2 class="title">Sos Fan Marolio - Restitrate</h2>
          <div class="container">
            <div class="row">
              <div class="col-md-6">
                <h2>Aquí</h2>
                <form>
                  <div class="mb-3">
                    <label for="nombre" class="form-label">Nombre</label>
                    <input type="text" class="form-control" id="nombre" required>
                  </div>
                  <div class="mb-3">
                    <label for="email" class="form-label">Email</label>
                    <input type="email" class="form-control" id="email" required>
                  </div>
                  <div class="mb-3">
                    <label for="password" class="form-label">Contraseña</label>
                    <input type="password" class="form-control" id="password" required>
                  </div>
                  <button type="submit" class="btn btn-primary">Registrarse</button>
                </form>
              </div>
              <div class="col-md-6">
                <h2>Login</h2>
                <form>
                  <div class="mb-3">
                    <label for="email" class="form-label">Email</label>
                    <input type="email" class="form-control" id="email" required>
                  </div>
                  <div class="mb-3">
                    <label for="password" class="form-label">Contraseña</label>
                    <input type="password" class="form-control" id="password" required>
                  </div>
                  <button type="submit" class="btn btn-primary">Iniciar sesión</button>
                </form>
              </div>
            </div>
          </div>
        </section>
      </section>
    </main>
    <Footer />
  </div>
</template>

<script>
import Header from 'src/components/Header.vue';
import Footer from 'src/components/Footer.vue';
import stockData from '@/assets/data/stock.json';

export default {
  name: 'App',
  components: {
    Header,
    Footer,
  },
  data() {
    return {
      stockData: stockData,
    };
  },
};
</script>

<style scoped>
@import '@/assets/buid.css';
</style>


