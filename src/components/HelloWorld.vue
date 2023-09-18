<script setup>
import { ref } from 'vue'

defineProps({
  msg: String,
})

const count = ref(0)
</script>

<template>
  <h1>{{ msg }}</h1>

  <!--<div class="card">
    <button type="button" @click="count++">count is {{ count }}</button>
    <p>
      Edit
      <code>components/HelloWorld.vue</code> to test HMR
    </p>
  </div>

  <p>
    Check out
    <a href="https://vuejs.org/guide/quick-start.html#local" target="_blank"
      >create-vue</a
    >, the official Vue + Vite starter
  </p>
  <p>
    Install
    <a href="https://github.com/johnsoncodehk/volar" target="_blank">Volar</a>
    in your IDE for a better DX
  </p>
  <p class="read-the-docs">Click on the Vite and Vue logos to learn more</p>-->
  <div class="card">
    <img alt="real estate logo" src="./housepic.jpg">
    <div class="card-content"> 
      <h2>Two Pod Realty</h2> 
      <p id="description">Real Estate Company Focused on delivering the best properties in the State College Area</p> 
      <button class="details-button" id="detailsBtn">Details</button>
    </div> 
  </div> 
  
  <button id="btn">Duplicator</button>
  <button id="colorBtn">BGColorChanger</button>
  <button id="Headingbtn">HeadingChanger</button>
  <button id="dltbtn">DeleteCard</button>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
