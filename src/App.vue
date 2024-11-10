<script setup>
import NavBar from './components/NavBar.vue';
import DatosPersonales from './components/DatosPersonales.vue';
import Educacion from './components/EducacionComponente.vue';
import Experiencia from './components/ExperienciaComponente.vue';
import Proyectos from './components/ProyectosComponente.vue';
import Habilidades from './components/HabilidadesComponente.vue';
import Intereses from './components/InteresesComponente.vue';
</script>

<template>
   <header id="top">
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
   <section id="habilidades"><h2>Habilidades</h2>
      <!--Componente habilidades-->
      <Habilidades/>
   </section>
   <section id="intereses"><h2>Intereses</h2>
      <!--Componente intereses-->
      <Intereses/>
   </section>
   </main>
   <footer>
      <a href="#top">Inicio</a>
      <p>© 2024 Leonela Huanca - Portafolio web</p>
   </footer>
</template>

<style scoped>
a{
   color:rgb(248, 248, 248);
}
footer{
   display: flex;
   flex-direction: column;
   align-items: center;
   padding: 2rem;
   font-size: 1.3rem;
   color:rgb(250, 246, 246);
}
</style>
