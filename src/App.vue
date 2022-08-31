<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <barra-lateral/>
    </div>
    <div class="column is-three-quarter">
      <formulario-app/>
    </div>
  </main>
</template>

<script lang="ts">
import FormularioApp from './components/Formulario.vue';
import { defineComponent } from 'vue';
import BarraLateral from './components/BarraLateral.vue';

export default defineComponent({
  components: { BarraLateral, FormularioApp },
  name: 'App',
});
</script> 

<style>
 
</style>
