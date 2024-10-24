<script setup>
import NavBar from './components/NavBar.vue';
import DatosPersonales from './components/DatosPersonales.vue';
import Educacion from './components/EducacionComponente.vue';
import Experiencia from './components/ExperienciaComponente.vue';
import Proyectos from './components/ProyectosComponente.vue';
</script>

<template>
   <header>
      <!--Barra de Navegacion-->
      <NavBar/>
      <!--Componente datos personales-->
      <DatosPersonales/>
   </header>
   <main>
   <section id="educacion"><h2>Educación - Cursos</h2>
      <!--Componente educacion-->
      <Educacion/>
   </section>
   <section id="experiencia"><h2>Experiencia</h2>
      <!--Componente experiencia-->
      <Experiencia/>
   </section>
   <section id="proyectos"><h2>Proyectos</h2>
      <!--Componente proyectos-->
      <Proyectos/>
   </section>
   <section id="habilidades"><h2>Habilidades</h2></section>
   <section id="intereses"><h2>Intereses</h2></section>
   </main>
</template>

<style scoped>

</style>
