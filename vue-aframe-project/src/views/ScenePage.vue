<template>
  <div>
    <a-scene>
      <a-assets>
        <!--
          To use a local model, place the model file in the `public` directory and update the src path.
          For example, if you have `public/my-model.glb`, the src would be `src="/my-model.glb"`.
        -->
        <a-asset-item id="animated-model" src="https://cdn.glitch.com/2372f4d9-b2d0-42e7-8898-c71d3434ac8f%2Fcube.glb?v=1597939174242"></a-asset-item>
        <audio id="sound" src="https://cdn.aframe.io/examples/audio/samples/chimes.wav" preload="auto"></audio>
      </a-assets>

      <a-sky color="#ECECEC"></a-sky>

      <a-entity
        gltf-model="#animated-model"
        position="0 1 -4"
        animation-mixer
        sound="src: #sound; autoplay: true; loop: true"
      ></a-entity>

      <a-camera>
        <a-cursor></a-cursor>
      </a-camera>
    </a-scene>

    <router-link to="/" class="back-button">Go to Home</router-link>
  </div>
</template>

<script setup>
import 'aframe';
import 'aframe-extras';
</script>

<style scoped>
.back-button {
  position: absolute;
  top: 20px;
  left: 20px;
  z-index: 10;
  padding: 10px;
  background-color: white;
  color: black;
  text-decoration: none;
  border-radius: 5px;
}
</style>
