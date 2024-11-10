<script setup>
import proyecto1 from '/src/assets/gestortareas.png';
import proyecto2 from '/src/assets/nuxtjs.png';
import proyecto3 from '/src/assets/restaurante.png';
import { ref } from 'vue';
var misProyectos = ref([]);
misProyectos.value = ([
    {
        id:1,
        src: proyecto1,
        titulo:"Sistema de Gestión de Tareas",
        descripcion:"Creé una aplicación de tareas colaborativa en React y Firebase con autenticación y actualización en tiempo real, mejorando la productividad en equipos remotos.",
        proyectoLink:"https://www.google.com.ar",
        githubLink:"https://github.com/usuario/proyecto"
    },
    {
        id:2,
        src: proyecto2,
        titulo:"Sitio Web de Portafolio Interactivo",
        descripcion:"Desarrollé mi portafolio con Nuxt.js, integrando animaciones y una galería de proyectos, optimizando la velocidad y SEO con renderizado del lado del servidor.",
        proyectoLink:"https://www.google.com.ar",
        githubLink:"https://github.com/usuario/proyecto"
    },
    {
        id:3,
        src: proyecto3,
        titulo:"Aplicación de Reservas para Restaurantes",
        descripcion:"Implementé una app de reservas con Vue.js y Express, permitiendo a los usuarios reservar mesas y recibir confirmaciones automáticas por correo, con una interfaz móvil intuitiva.",
        proyectoLink:"https://www.google.com.ar",
        githubLink:"https://github.com/usuario/proyecto"
    },
])
</script>

<template>
    <div class="galeria">
        <li class="proyecto" v-for="proyecto in misProyectos" :key="proyecto.id">
           <img :src="proyecto.src" :alt="proyecto.titulo">
           <div class="proyecto-info">
                <h3>{{ proyecto.titulo }}</h3>
                <p>{{ proyecto.descripcion }}</p>
                <div class="proyecto-links">
                    <a :href="proyecto.proyectoLink" clas="btn-ver-mas" target="_blank" rel="noopener noreferrer">Ver
                        Proyecto</a>
                    <a :href="proyecto.githubLink" class="github-link" target="_blank" rel="noopener noreferrer">Ver
                       Codigo en Github</a>
                </div>
            </div>
        </li>
    </div>
</template>

<style scoped>
.galeria{
    width: 100%;
    height: 100%;
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    padding: 20px;
    justify-content: center;
    background: linear-gradient(-45deg, #af1de9,#3d1adb,#20d3e0);
    background-size: 400% 400%;
    animation: gradient 15s ease infinite;
    border-radius: 15px;
}
@keyframes gradient{
    0%{
        background-position: 0% 50%;
    }

    50%{
        background-position: 100% 50%;
    }

    100%{
        background-position: 0% 50%;
    }
}
.proyecto{
    display: flex;
    flex-direction: column;
    border: 2px solid #ddd;
    border-radius: 8px;
    overflow: hidden;
    background-color: #080404;
    max-width: 222px;
    flex: 1 1 300px;
}
.proyecto img{
    width: 100%;
    height: auto;
    display: block;
}
.proyecto-info{
    padding: 15px;
    text-align: center;
}
.proyecto-info h3{
    margin: 10px 0;
    font-size: 1.3em;
    color: #362bd6;
}
.proyecto-info p{
    margin: 10px 0;
    font-size: 1em;
    color: #f4f0f5;
}
.proyecto-links{
    display: flex;
    flex-direction: column;
    gap: 10px;
    margin-top: 10px;
}
</style>
