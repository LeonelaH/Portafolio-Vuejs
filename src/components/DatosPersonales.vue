<script setup>
import Linkedin from '/src/assets/linkedin_icon.svg';
import Instagram from '/src/assets/instagram_icon.svg';
import Github from '/src/assets/github_icon.svg';
import Curriculum from '/src/assets/curriculum_icon.svg';

const title = 'Leonela Huanca';
const descripcion = 'Tecnico Universitario en Programacion - UTN';
const residencia = 'San Rafael, Mendoza, Argentina';
const presentacion = 'Bienvenido a mi portafolio, donde presento mis habilidades y proyectos como técnico en programación, combinando creatividad y lógica para resolver desafíos tecnológicos.';
const redesSociales =[
   { id: 1, name: 'Linkedin', src: Linkedin, url:'https:/www.linkedin.com/in/leonela-huanca/' },
   { id: 2, name: 'Instagram', src: Instagram, url:'https:/www.instagram.com/leonela-huanca/' },
   { id: 3, name: 'Github', src: Github, url:'https:/www.github.com/leonela-huanca/ '},
   { id: 4, name: 'Curriculum', src: Curriculum, url:'https:/www.curriculum.com/leonela-huanca/ '} 
];
const telefono = '+54 9 2604-685245';
</script>


<template>
    <section class="datos-personales">
        <div class="card">
          <h1>{{ title }}</h1>
          <h5>{{ descripcion }}</h5>
          <p>{{ presentacion }}</p>
          <ul class="container-lista">
            <li v-for="red in redesSociales" :key="red.id"> 
              <c :href="red.url"><img class="icon-redsocial" :src= "red.src" width="38rem" :alt="red.name"></c>
            </li>
          </ul>
          <h3>☏ Mi telefono personal: {{ telefono }}</h3>
          <h4>{{ residencia }}</h4>
        </div>
    </section>
</template>

<style scoped>
h1{
  color:rgb(248, 246, 246);
  font-size: 2.5rem;
}
h5{
  font-size: 2rem;
  color:rgb(243, 242, 242);
  margin-bottom: 1,5rem;
  text-align: center;
}

p{
  color:aliceblue;
  font-size: 1.2rem;
  font-weight: 600;
  margin-bottom: 1rem;
}

.card{
  background: linear-gradient(to right, #cf0c0c, #1616b6);
  border-radius: 15px;
  padding: 15px;
  margin: 10px;
  text-align: center;
}
.container-lista{
  display:flex;
  justify-content: center;
  list-style: none;
  padding: 0;
  margin: 0;
  text-align: center;
}
/*.icon-redsocial{
  align-items: center;
  background-color: transparent;
  border-radius: 46%;
  padding: 2px;
  margin: 5px;
  box-shadow: 0 0 5px rgba(10, 10, 10, 0.934);

}
.icon-redsocial:hover {
  background-color: white;
  box-shadow: 0 0 5px rgb(235, 223, 218);
  border: none;
}*/
.icon-redsocial {
  filter: invert(75%);
  transition: 0.2s;
  padding: 2px;
  margin: 6px;
}

.icon-redsocial:hover {
  filter: invert(100%);
  transition: 0.2s;
}

h3{
  font-size: 1.2rem;
  font-weight: 600;
}
h4{
  color:aliceblue;
}
</style>
