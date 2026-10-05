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
    defineEmits(['cerrar'])
</script>

<template>
    <div v-if="visible" class="fondo" @click.self="$emit('cerrar')">
        <article class="tarjeta">

            <div class="imagenes">
                <img :src="camiseta.imgs[0]" alt="">
                <img :src="camiseta.imgs[1]" alt="">
            </div>

            <select>
                <option>XS</option>
                <option>S</option>
                <option>M</option>
                <option>L</option>
                <option>XL</option>
            </select>

            <button @click="$emit('cerrar')">Cerrar</button>
            <button @click="$emit('añadir')">Añadir al carrito</button>

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
