
<script setup>
import { onMounted, ref } from 'vue';
const colors = ["#e03776", "#8f3e98", "#4687bf", "#3bab6f", "#f9c25e", "#f47274"] ;
const SVG_NS = 'http://www.w3.org/2000/svg';
const SVG_XLINK = "http://www.w3.org/1999/xlink";

let heartsRy = [];
const hearts = ref(null); // Referencia al SVG

function useTheHeart(n) {
  let use = document.createElementNS(SVG_NS, 'use');
  use.n = n;
  use.setAttributeNS(SVG_XLINK, 'xlink:href', '#heart');
  use.setAttributeNS(null, 'transform', `scale(${use.n})`);
  use.setAttributeNS(null, 'fill', colors[n % colors.length]);
  use.setAttributeNS(null, 'x', -69);
  use.setAttributeNS(null, 'y', -69);
  use.setAttributeNS(null, 'width', 138);
  use.setAttributeNS(null, 'height', 138);

  heartsRy.push(use);
  hearts.value.appendChild(use); // Añadir el símbolo al SVG referenciado
}
onMounted(() => {
  // Crear los corazones al montar el componente
  for (let n = 18; n >= 0; n--) {
    useTheHeart(n);
  }

  function Frame() {
    window.requestAnimationFrame(Frame);
    for (let i = 0; i < heartsRy.length; i++) {
      if (heartsRy[i].n < 18) {
        heartsRy[i].n += 0.01;
      } else {
        heartsRy[i].n = 0;
        hearts.value.appendChild(heartsRy[i]);
      }
      heartsRy[i].setAttributeNS(null, 'transform', `scale(${heartsRy[i].n})`);
    }
  }
  Frame(); // Iniciar la animación
});
</script>

<template>
  <div>
    <svg ref="hearts" id="hearts" viewBox="-600 -400 1200 800" preserveAspectRatio="xMidYMid slice">
      <defs>
        <symbol id="heart" viewBox="-69 -16 138 138">
          <path d="M0,12
                   C 50,-30 110,50  0,120
                   C-110,50 -50,-30 0,12z" />
        </symbol>
      </defs>
    </svg>
  </div>
</template>

<style scoped>

body {
  overflow: hidden;
  background-color: blueviolet;
}
svg {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 95%;
  z-index: -1;
  border-radius: 5px;
}

</style>
