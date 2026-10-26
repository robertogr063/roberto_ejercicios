<script setup>
import InterruptorVisibilidad from './components/interruptorVisibilidad.vue';


</script>

<template>
  <h1>Solución a los ejercicios de VUE</h1>
  <ul>
    <li>
      <router-link to="/interruptor">Vamos a interruptor</router-link>
    </li>
    <li>
      <router-link to="/examen">Vamos a examen</router-link>
    </li>
  </ul>
  <router-view/>
</template>
