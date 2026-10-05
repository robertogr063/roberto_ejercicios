```vue
<template>
    <header class="cabecera">
        <div class="contenido">

            <h1>
                Las camisetas de <strong>Manuel</strong>
            </h1>

            <p>Tu estilo. Tu camiseta.</p>
        </div>
    </header>
</template>

<style scoped>
.cabecera {
    background: linear-gradient(135deg, #111827, #1f2937);
    color: #ffffff;
    padding: 55px 20px;
    text-align: center;
    border-bottom: 4px solid #f59e0b;
}

.contenido {
    max-width: 1200px;
    margin: 0 auto;
}

.marca {
    display: inline-block;
    margin-bottom: 15px;

    color: #f59e0b;
    font-size: 14px;
    font-weight: 800;
    letter-spacing: 5px;
}

h1 {
    margin: 0;
    color: #ffffff;
    font-size: 42px;
    font-weight: 300;
    letter-spacing: 1px;
}

h1 strong {
    color: #ffffff;
    font-weight: 800;
}

p {
    margin: 15px 0 0;
    color: #d1d5db;
    font-size: 17px;
    letter-spacing: 1px;
}
</style>

