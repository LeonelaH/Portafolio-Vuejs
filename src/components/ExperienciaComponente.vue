<script setup>
import {ref} from 'vue';
const titulo='Desarrollador Web';
const fecha='Desde Enero 2021 / Octubre 2024';
const experiencias= ref([
    {id:1, src:'/src/assets/vuejs.svg', parrafo: 'He desarrollado aplicaciones web utilizando frameworks como Vue.js y React, enfocándome en crear interfaces de usuario intuitivas y responsivas.'},
    {id:2, src:'/src/assets/api.svg', parrafo: 'En varios proyectos, he integrado APIs RESTful, optimizando la comunicación entre el frontend y el backend para mejorar la experiencia del usuario.'},
    {id:3, src:'/src/assets/computer.svg', parrafo: 'He trabajado en la optimización de tiempos de carga y rendimiento, implementando técnicas como lazy loading, minificación de archivos y almacenamiento en caché.'},
    {id:4, src:'/src/assets/heroku.svg', parrafo: 'Tengo experiencia en el despliegue de aplicaciones web en entornos de producción utilizando plataformas como Netlify y Heroku, optimizando la entrega continua.'},
    {id:5, src:'/src/assets/git.svg', parrafo: 'He trabajado con herramientas de control de versiones como Git, facilitando la colaboración y el seguimiento de cambios en equipos de desarrollo ágiles.'},
]);
</script>

<template>
    <div class="card">
        <h3 class="titulo">{{ titulo.toLocaleUpperCase() }}</h3>
        <p class="fecha">{{ fecha }}</p>
        <ul class="listado">
            <li class="item" v-for="experiencia in experiencias" :key="experiencia.id">
                <img class="image-svg" :src="experiencia.src" width="45rem" :alt="experiencia.parrafo">
                <p>{{ experiencia.parrafo }}</p>
            </li>
        </ul>
    </div>
</template>

<style scoped>
.card{
    display: flex;
    flex-direction: column;
    padding: 2rem;
    background: linear-gradient(to right, #a7700b, #c43421);
    border-radius: 15px;
}
.titulo{
    font-size: 1.5rem;
    color:aliceblue;
}
.fecha{
    font-size: 1rem;
    color:aliceblue;
    margin-bottom: 1rem;
}
.listado{
    display: flex;
    flex-direction: column;
    color:rgb(255, 254, 254);
}
.item{
    align-items: center;
    display: flex;
    padding: 1rem;
    gap: 1.5rem;
}
</style>

