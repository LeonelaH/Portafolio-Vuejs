<template>
    <div class="timeline">
      <div v-for="(event, index) in events" :key="index" :class="['container', index % 2 === 0 ? 'left' : 'right']">
        <div class="content">
          <h2>{{ event.year }}</h2>
          <p>{{ event.description }}</p>
        </div>
      </div>
    </div>
</template>

<script>
  export default {
    data() {
      return {
        events: [
          { year: "2020", description: "Comence a aprender los fundamentos de la programación con Python y Git." },
          { year: "2021", description: "Me profundize en algoritmos, estructuras de datos y el desarrollo web con JavaScript." },
          { year: "2022", description: "Aprendí frameworks avanzados y contribui a proyectos más grandes, consiguiendo mi primer empleo  haciendo freelancing." },
          { year: "2023", description: "Me especialize en cloud computing, microservicios y participe en hackatones." },
          { year: "2024", description: "Explore inteligencia artificial, asumi roles de mentoría y colabore en la arquitectura de software." },
        ]
      };
    }
  };
</script>
  
<style scoped>
.timeline {
  position: relative;
  max-width: 800px;
  margin: 20px auto;
  color:azure;
}
.timeline::after {
  content: '';
  position: absolute;
  width: 6px;
  background-color: #181717;
  top: 0;
  bottom: 0;
  left: 50%;
  margin-left: -3px;
}
.container {
  padding: 10px 40px;
  position: relative;
  background-color: inherit;
  width: 50%;
}
.container.left {
  left: 0;
}
.container.right {
  left: 50%;
}
.content {
  padding: 20px;
  background: linear-gradient(to right, #2bd8f7, #2743c0);
  position: relative;
  border-radius: 6px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}
.container.left::before {
  content: " ";
  position: absolute;
  top: 15px;
  right: -15px;
  border-width: 15px;
  border-style: solid;
  border-color: transparent rgb(41, 199, 75) transparent transparent;
}
/*.container.right::before {
  content: " ";
  position: absolute;
  top: 15px;
  left: -15px;
  border-width: 15px;
  border-style: solid;
  border-color: transparent transparent transparent rgb(5, 207, 207);
}*/
.container.left .content {
  margin-left: 20px;
}
.container.right .content {
  margin-right: 20px;
}
h2 {
  color: #03007a;
}
/* Media queries para dispositivos móviles */
@media screen and (max-width: 768px) {
  .timeline::after {
    left: 10px;
  }
  .container {
    width: 100%;
    padding-left: 70px;
    padding-right: 25px;
  }
  .container.left, .container.right {
    left: 0;
  }
  .container.left::before, .container.right::before {
    left: 60px;
    border-color: transparent transparent transparent rgb(32, 161, 75);
  }
  .content {
    margin-left: 0;
    margin-right: 0;
    padding-left: 20px;
  }
  .container.left .content, .container.right .content {
    max-width: 100%; /* Elimina el ancho máximo en móvil */
  }
}
</style>