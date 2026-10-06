<script setup>

  defineProps({
    visible: {
      type: Boolean,
      default: false
    },
    productos: {
      type: Array,
      default: () => []
    }
  })
  defineEmits(['cerrar'])
</script>
<template>
  <div class="fondo" v-if="visible" @click.self="$emit('cerrar')">
    <article class="carrito">
      <div class="cabecera-carrito">
        <h2>Tu carrito</h2>
        <button class="cerrar" @click="$emit('cerrar')">×</button>
      </div>

      <div class="productos">

        <div v-for="producto in productos" class="producto">
          <div>
            <strong>{{ producto.nombre }}</strong>
            <p>Talla: {{ producto.talla }}</p>
            <p>Cantidad: {{producto.cantidad }}</p>
          </div>

          <span>{{ producto.precio }} €</span>
        </div>

      </div>

      <div class="total">
        <span>Total</span>
        <!--<strong>{{ precioTotal }} €</strong>--->
      </div>
      <button class="comprar">Finalizar compra</button>
    </article>
  </div>
</template>

<style scoped>
.fondo {
  position: fixed;
  inset: 0;
  background: rgba(0, 0, 0, 0.6);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
}

.carrito {
  width: 500px;
  max-width: 90%;
  background: white;
  border-radius: 18px;
  padding: 30px;
  box-sizing: border-box;
  box-shadow: 0 15px 40px rgba(0, 0, 0, 0.25);
}

.cabecera-carrito {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 25px;
}

.cabecera-carrito h2 {
  margin: 0;
  color: #111827;
  font-size: 28px;
}

.cerrar {
  border: none;
  background: none;
  font-size: 30px;
  color: #6b7280;
  cursor: pointer;
}

.productos {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.producto {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px;
  background: #f3f4f6;
  border-radius: 10px;
}

.producto strong {
  color: #111827;
}

.producto p {
  margin: 5px 0 0;
  color: #6b7280;
}

.producto span {
  font-weight: bold;
  color: #111827;
}

.total {
  display: flex;
  justify-content: space-between;
  margin-top: 25px;
  padding-top: 20px;
  border-top: 1px solid #e5e7eb;
  font-size: 20px;
  color: #111827;
}

.comprar {
  width: 100%;
  margin-top: 25px;
  padding: 14px;
  border: none;
  border-radius: 10px;
  background: #f59e0b;
  color: white;
  font-size: 16px;
  font-weight: bold;
  cursor: pointer;
}

.comprar:hover {
  background: #d97706;
}
</style>