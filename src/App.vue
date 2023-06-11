<script setup>
import {ref, computed} from 'vue'
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
const name = "Mi numero";
  const arrayfavoritos = ref([]);

  const bloquearfavorito = computed(() => {
    const numeroBuscar =  arrayfavoritos.value.find(num => num === conter.value)
    return numeroBuscar ? true : numeroBuscar === 0 ? true : false;
  })

  const conter = ref(0);
  const incremet = () =>{
    console.log("estoy sumando +1");
    conter.value++;
  }
  const decrementar = () => {
    conter.value--;
  }
  const reset = () =>{
    conter.value = 0;
  }
  const favorito = () => {
    arrayfavoritos.value.push(conter.value)
  }
  const red = "color:red;";
  const green = "color:green";
</script>

<template>
  <div class="container text-center">
    
    <h1>{{ name.toUpperCase() }} </h1>
    <h2 :style="conter >= 0 ? green : red">{{ conter }}</h2>
    <div class="d-grid gap-2 d-md-block">
      <button type="button" class="me-2 btn btn-outline-primary" @click="incremet">Aumentar</button>
      <button type="button" class="me-2 btn btn-outline-danger" @click="decrementar">Disminuir</button>
      <button type="button" class="me-2 btn btn-outline-info" @click="reset">Resetear</button>
      <button type="button" class="me-2 btn btn-outline-warning" @click="favorito" :disabled="bloquearfavorito">Favorito</button>
    </div>
    <h2 class="mt-4">Mis favoritos</h2>
    <ul>
      <li v-for="(numero, index) in arrayfavoritos" :key="index">
      {{ numero }}
      </li>
    </ul>
    <table>
  
    </table>
  </div>
</template>

<style scoped>


</style>
