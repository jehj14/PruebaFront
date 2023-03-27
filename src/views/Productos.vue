<script setup lang='ts'>
import Read from '@/components/Read.vue'
import Update from '@/components/Update.vue'
import Create from '@/components/Create.vue'
import { ref } from 'vue';
let Lista  = [ { nombre: 'asfs', codigo: '0123', descipcion: 'fafawfwef', precio: '500' },{ nombre: 'hjjgjh', codigo: '0124', descipcion: 'khbjhbjh', precio: '500' },{ nombre: 'gfhgg', codigo: '0125', descipcion: 'adasdasda', precio: '500' }];
let showCrear = ref(false)
function mostrarCrear() {
  this.showCrear= !this.showCrear

}
</script>

<template>
  <div class="about">
    <div class="container1">
      <h1>Lista de productos</h1>
      <Read :productos='Lista'/>
      <button id="btn-showCrear" type="button" @click="mostrarCrear()">Crear Nuevo</button>
    </div>
    <div class="container2">
      <Create  v-if="showCrear"/>
    </div>
    <div class="container3">
      <h1>Actualizar Productos</h1>
      <Update :form='Lista[2]'/>
    </div>
  </div>
</template>

<style>
#btn-showCrear{
  width: 6rem;
  height: 2.5rem;
  border-radius: 0.8rem;
  margin: 1rem;
}

#btn-showCrear:hover{
  background: rgb(153, 145, 145);
  color: rgb(255, 255, 255);
  cursor: pointer;
}

.about{
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}

.container1, .container2, .container3 {
  width: 40%;
  height: 40%;
  margin-left: 5%;
  margin-right: 5%;
  margin-bottom: 5%;
}

.container1, .container3 {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.container3 {
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
}

h1 {
  padding-bottom: 0.5rem;
}

@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
  }
}
</style>
