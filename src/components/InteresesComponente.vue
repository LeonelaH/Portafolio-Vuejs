<script setup>
import { ref } from 'vue';
import FondoLava from './FondoLava.vue';
const intereses = ref([
    'Seguridad Web: Me comprometo a proteger mis aplicaciones contra vulnerabilidades, implementando prácticas que resguarden tanto los datos como la privacidad de los usuarios.',
    'Optimización de rendimiento: Disfruto mejorando la velocidad de carga de las páginas y la eficiencia del código, buscando siempre el balance perfecto entre estética y rendimiento.',
    'Experiencia del Usuario: Me interesa comprender cómo los usuarios interactúan con los sitios, buscando formas de hacer que la navegación sea fluida y satisfactoria.',
    'Viajar y explorar nuevas culturas: Disfruto descubrir lugares nuevos y aprender de distintas culturas, ya que me inspira tanto en lo personal como en lo profesional.'
])
</script>

<template>
    <div class="intereses-contenedor">
        <FondoLava/>
        <ul class="contenedor-lista">
            <li class="item" v-for="interes in intereses" :key="interes">
                {{ interes }}   
            </li>
        </ul>
    </div>
</template>


<style scoped>
.intereses-contenedor{
    display: flex;
    position: relative;
    margin: 0 auto;
    max-width: 85%;
    padding: 1rem;
}

.contenedor-lista{
    list-style-type: none;
    padding: 1rem;
    margin-bottom: .5rem;
    color: rgb(255, 255, 255);
    font-size: 1.4rem;
    z-index: 2;
}

.item{
    margin-bottom: 1rem;
}

</style>
