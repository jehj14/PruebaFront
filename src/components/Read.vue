<script setup lang="ts">
defineProps({
  productos:Array
})
function eliminarItem(item: number) {
  console.log('se elimino el item',item)
}
</script>

<template>
  <div class="greetings">
    <h1 class="green"></h1>
    <h3>
      <table class="default">
        <tr>
          <th>Nombre</th>

          <th>Codigo</th>

          <th>Descipcion</th>

          <th>Precio</th>

          <th>Eliminar</th>
        </tr>

        <tr v-for="(producto,index) in productos" :key="index">
          <td>{{producto.nombre}}</td>

          <td>{{producto.codigo}}</td>

          <td>{{producto.descipcion}}</td>

          <td>{{producto.precio}}</td>

          <td @click="eliminarItem(index)">Eliminar</td>
        </tr>
      </table>
    </h3>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
