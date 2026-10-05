<template>
    <footer class="pie">
        <div class="pie-contenido">

            <div class="marca">
                <span>MANUEL®</span>
                <p>
                    Camisetas para todos los estilos.
                    Viste diferente, viste Manuel.
                </p>
            </div>

            <div class="enlaces">
                <h3>TIENDA</h3>
                <a href="#">Colección</a>
                <a href="#">Novedades</a>
                <a href="#">Ofertas</a>
            </div>

            <div class="contacto">
                <h3>CONTACTO</h3>
                <p>manuel@camisetas.com</p>
                <p>+34 600 123 456</p>
                <p>España</p>
            </div>

        </div>

        <div class="pie-final">
            <span>© 2026 Manuel. Todos los derechos reservados.</span>
            <span>Hecho con estilo.</span>
        </div>
    </footer>
</template>

<style scoped>
.pie {
    margin-top: 60px;
    background: #111827;
    color: white;
}

.pie-contenido {
    max-width: 1200px;
    margin: 0 auto;
    padding: 55px 30px;

    display: grid;
    grid-template-columns: 2fr 1fr 1fr;
    gap: 60px;
}

.marca span {
    color: #f59e0b;
    font-size: 24px;
    font-weight: 800;
    letter-spacing: 4px;
}

.marca p {
    max-width: 350px;
    margin-top: 15px;
    color: #9ca3af;
    line-height: 1.6;
}

h3 {
    margin: 0 0 18px;
    color: #f59e0b;
    font-size: 14px;
    letter-spacing: 2px;
}

.enlaces {
    display: flex;
    flex-direction: column;
    gap: 10px;
}

.enlaces a {
    color: #d1d5db;
    text-decoration: none;
    transition: color 0.2s, transform 0.2s;
}

.enlaces a:hover {
    color: #f59e0b;
    transform: translateX(4px);
}

.contacto p {
    margin: 8px 0;
    color: #9ca3af;
}

.pie-final {
    border-top: 1px solid #374151;
    padding: 20px 30px;

    display: flex;
    justify-content: space-between;

    color: #6b7280;
    font-size: 13px;
}
</style>