<script setup>
import { ref } from 'vue';
const habilidades = ref([
    {
        id: 1, nombre: 'Lenguajes de Programación', habilidades: [
            { id: 1, nombre: 'Python', nivel:'Intermedio', icono: '/src/components/icons/python.svg'},
            { id: 2, nombre: 'JavaScript', nivel:'Avanzado', icono: '/src/components/icons/javascript.svg'},
            { id: 3, nombre: 'Java', nivel:'Avanzado', icono: '/src/components/icons/java.svg'},
            { id: 4, nombre: 'C++', nivel:'Intermedio', icono: '/src/components/icons/c++.svg'}
        ]
    },
    {   
        id: 2, nombre: 'Frameworks y Librerias', habilidades: [
            { id: 1, nombre: 'Vue.js', nivel:'Avanzado', icono: '/src/components/icons/vuejs.svg'},
            { id: 2, nombre: 'Django', nivel:'Intermedio', icono: '/src/components/icons/django.svg'},
            { id: 3, nombre: 'Node.js', nivel:'Avanzado', icono: '/src/components/icons/nodejs.svg'},
            { id: 4, nombre: 'React.js', nivel:'Avanzado', icono: '/src/components/icons/reactjs.svg'}
        ]
    },
    {   
        id:3, nombre: 'Herramientas y Software', habilidades: [
           {id: 1, nombre: 'Git', nivel:'Avanzado', icono: '/src/components/icons/git.svg'},
           {id: 2, nombre: 'Visual Studio', nivel:'Avanzado', icono: '/src/components/icons/visualstudiocode.svg'},
           {id: 3, nombre: 'Cypress', nivel:'Intermedio', icono: '/src/components/icons/cypress.svg'},
           {id: 4, nombre: 'Selenium', nivel:'Intermedio', icono: '/src/components/icons/selenium.svg'}
        ]
    },
    {   
        id:4, nombre: 'Base de Datos', habilidades: [
           {id: 1, nombre: 'MySQL', nivel:'Avanzado', icono: '/src/components/icons/mysql.svg'},
           {id: 2, nombre: 'Oracle', nivel:'Intermedio', icono: '/src/components/icons/oracle.svg'}
        ]
    },
    {   
        id:5, nombre: 'Idiomas', habilidades: [
           {id: 1, nombre: 'Español', nivel:'Nativo', icono: '/src/components/icons/español.svg'},
           {id: 2, nombre: 'Ingles', nivel:'Avanzado', icono: '/src/components/icons/ingles.svg'},
           {id: 3, nombre: 'Portugues', nivel:'Intermedio', icono: '/src/components/icons/portugues.svg'}
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
    background-image: url('/src/assets/imagen.jpg');/*imagen de fondo*/
    background-size: cover;
    background-position: bottom center;
    background-repeat: no-repeat;
    background-attachment: fixed;
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
    background-color: #f887d6;
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