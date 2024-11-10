<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const followElement = ref(null);

const handleMouseMove = (event) => {
  if (followElement.value) {
    const mouseX = event.clientX;
    const mouseY = event.clientY;

    const elementWidth = followElement.value.offsetWidth;
    const elementHeight = followElement.value.offsetHeight;

    const newX = mouseX - elementWidth / 2;
    const newY = mouseY - elementHeight / 2;

    followElement.value.style.left = `${newX}px`;
    followElement.value.style.top = `${newY}px`;
  }
};

onMounted(() => {
  document.body.addEventListener('mousemove', handleMouseMove);
});

onUnmounted(() => {
  document.body.removeEventListener('mousemove', handleMouseMove);
});
</script>

<template>
  <div class="canvas">
    <div class="blur">
      <div class="circle circle-center"></div>
      <div class="circle circle-followed" ref="followElement"></div>
    </div>
    <div class="filter filter-dodge"></div>
    <div class="filter filter-burn"></div>    
  </div>
</template>

<style scoped>

body {
  height: 100vh;
  background-image: linear-gradient(90deg, #00DBDE 0%, #FC00FF 100%);
  overflow: hidden;
}

.canvas {
  top: 10px;
  left: 10px;
  right: 10px;
  bottom: 10px;
  position: absolute;
  background: lemonchiffon;
  overflow: hidden;
  mix-blend-mode: screen;
}

.blur {
  filter: blur(40px);
  height: 100%;
}

.circle-followed {
  cursor: none;
  background: radial-gradient(circle, #00DBDE, #8d138f);
  border: 2px solid rgba(255, 255, 255, 0.3); 
  width: 150px; 
  aspect-ratio: 1 / 1;
}

.filter {
  pointer-events: none;
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}

.filter-dodge {
  background: #3f95af;
  mix-blend-mode: color-dodge;
}

.filter-burn {
  background: black;
  mix-blend-mode: color-burn;
}

.circle {
  position: absolute;
  display: block;
  width: 200px;
  aspect-ratio: 1 / 1;
  background: black;
  border-radius: 100%;
  margin-bottom: 10px;
}

.circle-center {
  top: 50%;
  left: 50%;
  width: 300px;
  transform: translateX(-50%) translateY(-50%);
}

body:not(:hover) .circle-followed {
  animation: move 3s cubic-bezier(0, 0.37, 1, 0.66) infinite;
  animation-direction: alternate-reverse;
}

@keyframes move {
  0% {
    top: -10%;
    left: -10%;
  }

  100% {
    top: 80%;
    left: 80%;
  }
}

</style>
