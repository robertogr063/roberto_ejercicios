<script setup>
import { ref } from 'vue'
import stwd from '../assets/stwd.jpg'
import nike from '../assets/nike.jpg'
import adidas from '../assets/adidas.jpg'
import under_armour from '../assets/under_armour.avif'
import john_smith from '../assets/john_smith.avif'
import fila from '../assets/fila.jpg'

const count = ref(0)
const total = ref(0)
let camisetas = [
  { nombre: "stwd", precio: 15, imagen: stwd},
  {nombre: "Nike", precio: 25, imagen: nike},
  {nombre: "Adidas", precio: 35, imagen: adidas},
  {nombre: "Under Armour", precio: 5, imagen: under_armour},
  {nombre: "John Smith", precio: 150, imagen: john_smith},
  {nombre: "Fila", precio: 10, imagen: fila}
]
</script>
<template>
  <div>Total {{ total }}</div>
  <div class="modelos rejilla">

    <article v-for="camiseta in camisetas" :key="camiseta.nombre" class="precio_wrap">
      <p>
        <img :src="camiseta.imagen" alt=""> 
      </p>
      <div class="info">
        <strong class="camiseta">{{ camiseta.nombre }}</strong>
        <span class="precio">: {{ camiseta.precio }}</span>
      </div>
      <button type="button" class="counter" @click="total += camiseta.precio">
        Añadir
      </button>
    </article>


  </div>
</template>

<style scope>
.info{
  display: flex;

}
    
    article{
        width: 50%;
        margin: 2em;
        box-shadow: 10px 10px;
        border-radius: lem;
        background-color: antiquewhite;
        float: left;
    }

    .catalogo{
        clear: both;
    }
     img{
        width: 70px;
        height: 50px;
     }


.modelos {
  max-width: 1200px;
  margin: auto;
  padding: 70px 24px;
  text-align: center;
}

.rejilla {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 24px;
}

article {
  background: #f1f5f9;
  border-radius: 14px;
  padding: 24px;
  text-align: left;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.08);
  transition: transform 0.2s, box-shadow 0.2s;
}

article:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 18px rgba(0, 0, 0, 0.12);
}

article img {
  width: 100%;
  height: 220px;
  object-fit: cover;
  border-radius: 10px;
}

article h2 {
  margin: 16px 0 8px;
  color: #1e293b;
}

article p {
  color: #64748b;
  line-height: 1.5;
}

</style>