<script setup lang="ts">
import { ref } from "vue";
defineProps<{
  form :any
  msg: string
}>()
function guardar(){
  console.log('guardado')
 
  if (this.form.nombre != '' && this.form.codigo !='' && this.form.descipcion !='' && this.form.precio !=''){
     console.log(this.form.nombre)
  console.log(this.form.codigo)
  console.log(this.form.descipcion)
  console.log(this.form.precio)
  }
}
</script>

<template>
  <div class="greetings">
    <h3>
      <form>
        <ul>
          <li>
            <label for="name">Nombre Del producto:{{ form.nombre }}</label>
            <input v-model="form.nombre" type="text" id="name" name="user_name" />
          </li>
          <li>
            <label for="Codigo">Codigo Del producto:{{form.codigo}}</label>
            <input v-model="form.codigo" type="number" id="Codigo" name="user_Codigo" />
          </li>
          <li>
            <label for="Descipcion">Agregue Una Descipcion Al producto:{{form.descripcion}}</label>
            <textarea v-model="form.descipcion" id="Descripcion" name="user_Descripcion"></textarea>
          </li>
          <li>
            <label for="Precio">Ingrese el Precio Del producto:{{form.precio}}</label>
            <input v-model="form.precio" type="number" id="Precio" name="user_Precio" />
          </li>
        </ul>
        <button @click="guardar()" type="button">Agregar</button>
      </form>
    </h3>
  </div>
</template>

<style scoped>

.greetings {
  display: flex;
  flex-direction: column;
  align-items: center;
}

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

button{
  width: 6rem;
  height: 2.5rem;
  border-radius: 0.8rem;
  margin: 1rem;
}

button:hover{
  background: rgb(153, 145, 145);
  color: rgb(255, 255, 255);
  cursor: pointer;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
