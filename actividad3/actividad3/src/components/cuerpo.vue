<script setup>
import { ref } from 'vue'
import detalle from './detalle.vue'
import stwd from '../assets/stwd.jpg'
import nike from '../assets/nike.jpg'
import adidas from '../assets/adidas.jpg'
import under_armour from '../assets/under_armour.avif'
import john_smith from '../assets/john_smith.avif'
import fila from '../assets/fila.jpg'
import stwd_vuelta from '../assets/stwd_vuelta.webp'
import nike_vuelta from '../assets/nike_vuelta.avif'
import adidas_vuelta from '../assets/adidas_vuelta.avif'
import under_armour_vuelta from '../assets/under_armour_vuelta.avif'
import john_smith_vuelta from '../assets/john_smith_vuelta.webp'
import fila_vuelta from '../assets/fila_vuelta.avif'

const total = ref(0)
const visible = ref(false)
const camisetaSeleccionada = ref(null);

let carrito = [];
let camisetas = [
  {
    nombre: "stwd",
    precio: 15,
    imgs: [
      stwd,
      stwd_vuelta
    ],
    tallas: {
      xs: 1,
      s: 2,
      m: 0,
      l: 8,
      xl: 0
    }
  },
  {
    nombre: "Nike",
    precio: 25,
    imgs: [
      nike,
      nike_vuelta
    ],
    tallas: {
      xs: 3,
      s: 5,
      m: 2,
      l: 0,
      xl: 4
    }
  },
  {
    nombre: "Adidas",
    precio: 35,
    imgs: [
      adidas,
      adidas_vuelta
    ],
    tallas: {
      xs: 0,
      s: 6,
      m: 4,
      l: 3,
      xl: 1
    }
  },
  {
    nombre: "Under Armour",
    precio: 5,
    imgs: [
      under_armour,
      under_armour_vuelta
    ],
    tallas: {
      xs: 2,
      s: 0,
      m: 7,
      l: 5,
      xl: 3
    }
  },
  {
    nombre: "John Smith",
    precio: 150,
    imgs: [
      john_smith,
      john_smith_vuelta
    ],
    tallas: {
      xs: 1,
      s: 2,
      m: 3,
      l: 1,
      xl: 0
    }
  },
  {
    nombre: "Fila",
    precio: 10,
    imgs: [
      fila,
      fila_vuelta
    ],
    tallas: {
      xs: 4,
      s: 3,
      m: 0,
      l: 6,
      xl: 2
    }
  }
]
  function anadirAlCarrito(camisetaCarrito) {
    if(camisetaCarrito.talla !== undefined){
        console.log(camisetaCarrito)
    }
    
}

</script>
<template>
  <div>Total {{ total }}</div>
  <div class="modelos rejilla">

    <article v-for="camiseta in camisetas" :key="camiseta.nombre" class="precio_wrap">
      <p>
        <img class="cliclable"
          :src="camiseta.imgs[0]"
          alt=""
          @click="camisetaSeleccionada = camiseta;visible = true"
        >
      </p>
      <div class="info">
        <strong class="camiseta">{{ camiseta.nombre }}</strong>
      </div>
      <button type="button" class="counter" @click="total += camiseta.precio" >
        
        Añadir
      </button>
    </article>


  </div>
  <!--Modal-->
  <detalle
    :visible="visible"
    :camiseta="camisetaSeleccionada"
    @cerrar="visible = false"
    @añadir="anadirAlCarrito"
    
  />
</template>

<style scope>

/* Configuración general */
html,
body {
    margin: 0;
    padding: 0;
}

/* Información dentro de las tarjetas */
.info {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

/* Catálogo */
.catalogo {
    clear: both;
}

/* Contenedor de los modelos */
.modelos {
    width: 100%;
    max-width: 1200px;
    margin: 0 auto;
    padding: 50px 20px;
    box-sizing: border-box;
    text-align: center;
}

/* Rejilla de productos */
.rejilla {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 30px;
}

/* Tarjetas */
article {
    background: #ffffff;
    border-radius: 18px;
    padding: 20px;
    text-align: left;
    box-shadow: 0 5px 20px rgba(0, 0, 0, 0.08);
    transition: transform 0.2s ease, box-shadow 0.2s ease;
}

/* Efecto al pasar el ratón */
article:hover {
    transform: translateY(-6px);
    box-shadow: 0 12px 25px rgba(0, 0, 0, 0.14);
}

/* Imagen de cada camiseta */
article img {
    display: block;
    width: 100%;
    height: 260px;
    object-fit: cover;
    border-radius: 14px;
}

/* Títulos */
article h2 {
    margin: 16px 0 8px;
    color: #172033;
    font-size: 22px;
}

/* Texto */
article p {
    margin: 8px 0;
    color: #64748b;
    line-height: 1.5;
}

/* Elementos que se puedan pulsar */
.cliclable {
    cursor: pointer;
}

/* Precio */
.precio {
    font-weight: bold;
    color: #172033;
}

/* Nombre de la camiseta */
.camiseta {
    font-size: 18px;
    color: #172033;
}




</style>