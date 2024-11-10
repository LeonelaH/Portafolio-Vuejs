<script setup>
import img1 from '/src/components/icons/python.svg';
import img2 from '/src/components/icons/javascript.svg';
import img3 from '/src/components/icons/java.svg';
import img4 from '/src/components/icons/c++.svg';

import img5 from '/src/components/icons/vuejs.svg';
import img6 from '/src/components/icons/django.svg';
import img7 from '/src/components/icons/nodejs.svg';
import img8 from '/src/components/icons/reactjs.svg';

import img9 from '/src/components/icons/git.svg';
import img10 from '/src/components/icons/visualstudiocode.svg';
import img11 from '/src/components/icons/cypress.svg';
import img12 from '/src/components/icons/selenium.svg';

import img13 from '/src/components/icons/mysql.svg';
import img14 from '/src/components/icons/oracle.svg';

import img15 from '/src/components/icons/español.svg';
import img16 from '/src/components/icons/ingles.svg';
import img17 from '/src/components/icons/portugues.svg';

import { ref } from 'vue';
const habilidades = ref([
    {
        id: 1, nombre: 'Lenguajes de Programación', habilidades: [
            { id: 1, nombre: 'Python', nivel:'Intermedio', icono: img1},
            { id: 2, nombre: 'JavaScript', nivel:'Avanzado', icono: img2},
            { id: 3, nombre: 'Java', nivel:'Avanzado', icono: img3},
            { id: 4, nombre: 'C++', nivel:'Intermedio', icono: img4}
        ]
    },
    {   
        id: 2, nombre: 'Frameworks y Librerias', habilidades: [
            { id: 1, nombre: 'Vue.js', nivel:'Avanzado', icono: img5},
            { id: 2, nombre: 'Django', nivel:'Intermedio', icono: img6},
            { id: 3, nombre: 'Node.js', nivel:'Avanzado', icono: img7},
            { id: 4, nombre: 'React.js', nivel:'Avanzado', icono: img8}
        ]
    },
    {   
        id:3, nombre: 'Herramientas y Software', habilidades: [
           {id: 1, nombre: 'Git', nivel:'Avanzado', icono: img9},
           {id: 2, nombre: 'Visual Studio', nivel:'Avanzado', icono: img10},
           {id: 3, nombre: 'Cypress', nivel:'Intermedio', icono: img11},
           {id: 4, nombre: 'Selenium', nivel:'Intermedio', icono: img12}
        ]
    },
    {   
        id:4, nombre: 'Base de Datos', habilidades: [
           {id: 1, nombre: 'MySQL', nivel:'Avanzado', icono: img13},
           {id: 2, nombre: 'Oracle', nivel:'Intermedio', icono: img14}
        ]
    },
    {   
        id:5, nombre: 'Idiomas', habilidades: [
           {id: 1, nombre: 'Español', nivel:'Nativo', icono: img15},
           {id: 2, nombre: 'Ingles', nivel:'Avanzado', icono: img16},
           {id: 3, nombre: 'Portugues', nivel:'Intermedio', icono: img17}
        ]
    }
]);
</script>

<template>
    <div class="skills-contenedor">
        <div v-for="habilidad in habilidades" :key="habilidad.id" class="skills-categoria">
            <h3>{{ habilidad.nombre }}</h3>
            <ul  class="skills">
                <li v-for="habilidad in habilidad.habilidades" :key="habilidad.id" class="skill">
                    <img :src="habilidad.icono" :alt="habilidad.nombre">
                    <span>{{ habilidad.nombre }}: {{ habilidad.nivel }}</span>
                </li>
            </ul>
        </div>
    </div>
</template>

<style scoped>
.skills-contenedor {
    padding: 2rem;
    /*background-image: url('/src/assets/imagen.jpg');
    background-size: cover;
    background-position: bottom center;
    background-repeat: no-repeat;
    background-attachment: fixed;*/
    background: linear-gradient(-45deg, #1c34b9,#3bbbcc,#7e0b7e,#e9f549,#5ee942);
    border-radius: 15px;
}
.skills-categoria{
    margin-bottom: 20px;
}
.skills-categoria h3{
    display:flex;
    justify-content: left;
    margin-bottom: 10px;
    font-size: 1.5rem;
    color:rgb(255, 253, 253);
    font-size: 1.5rem;
    font-weight: bold;
}
.skills{
    display: flex;
    justify-content: space-evenly;
    flex-wrap: wrap;
    gap: 20px;
}
.skill{
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 10px;
    background-color: rgb(0, 0, 0);
    padding: 0.3em;
    border-radius: 8px;
    flex: 1 1 200px;
    max-width: 250px;
}
.skill:hover{
    background-color: #837b81;
}
.skill img{
    width: 35px;
    height: 35px;
}
.skill span{
    color: #f2f2f7;
    overflow: hidden;
    position: relative;
}
.skill:hover{
    transform: translateX(10px); /* Cambia a otra dirección */
    transition: transform 0.3s ease;
}

@media (max-width: 768px){
    .skills-categoria h3{
        justify-content: center;
    }
    .skill{
        justify-content: center;
    }
}
</style>