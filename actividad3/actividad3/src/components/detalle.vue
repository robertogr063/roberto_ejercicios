<script setup>
    defineProps({
        visible: {
            type: Boolean,
            default: false
        }
    })
    defineEmits(['cerrar'])
</script>

<template>

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
</style>
