<script setup>
    defineProps({
        visible: {
            type: Boolean,
            default: false
        },
        camiseta: {
            type: Object,
            default: null
    }
    })
    const emit = defineEmits(['cerrar', 'añadir'])

    function anadirCamiseta(nombre, talla, precio){
        let camisetaCarrito = {
            nombre : nombre,
            talla: talla,
            precio: precio,
            cantidad: 1
        }
        emit('añadir', camisetaCarrito)
    }
</script>

<template>
    <div v-if="visible" class="fondo" @click.self="$emit('cerrar')">
        <article class="tarjeta">

            <div class="imagenes">
                <img :src="camiseta.imgs[0]" alt="">
                <img :src="camiseta.imgs[1]" alt="">
            </div>
            Precio: {{ camiseta.precio }}

            <select v-model="talla">
                <template v-for="(disponibilidad, tallaDisponible) in camiseta.tallas" :key="tallaDisponible">
                    <option v-if="disponibilidad > 0" :value="tallaDisponible">
                        {{ tallaDisponible.toUpperCase() }} - {{ disponibilidad }} disponibles
                    </option>
                </template>
            </select>

            <button @click="$emit('cerrar')">Cerrar</button>

            <button @click="anadirCamiseta(camiseta.nombre, talla, camiseta.precio)">
                Añadir al carrito
            </button>

        </article>
    </div>
</template>

<style scoped>
.fondo {
    position: fixed;
    inset: 0;
    background: rgba(23, 32, 51, 0.6);
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 24px;
    z-index: 100;
}

.tarjeta {
    width: 90%;
    max-width: 700px;
    padding: 25px;
    border-radius: 20px;
    background-color: white;
    display: flex;
    flex-direction: column;
    gap: 20px;
}

.imagenes {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 15px;
}

.imagenes img {
    width: 100%;
    height: 250px;
    object-fit: cover;
    border-radius: 12px;
}

select {
    padding: 10px;
    border-radius: 8px;
}

button {
    padding: 10px 20px;
    border: none;
    border-radius: 8px;
    cursor: pointer;
}

button + button {
    margin-left: 10px;
}
</style>
