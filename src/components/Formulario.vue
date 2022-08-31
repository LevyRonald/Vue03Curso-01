<template>
  <div class="box">
    <div class="columns">
      <div
        class="column is-8"
        role="form"
        aria-label="Formulario para criação de uma nova tarefa"
      >
        <input
          type="text"
          class="input"
          placeholder="qual tarefa você deseja iniciar?"
          v-model="descricao"
        />
      </div>
      <div class="column">
        <temporizador-formulario @aoTemporizadorFinalizado="finalizarTarefa"/>
      </div>
    </div>
  </div>
</template>
<script lang="ts">
import TemporizadorFormulario from "./Temporizador.vue";
import { defineComponent } from "vue";

export default defineComponent({
  components: { TemporizadorFormulario },
  name: "FormularioApp",
  data() {
    return {
        descricao: ''
    }
  },
  methods: {
    finalizarTarefa(tempoDecorrido: number): void  {
        console.log('tempo da tarefa', tempoDecorrido)
        console.log('descrição da tarefa', this.descricao)
        this.descricao = ''
    }
  }
});
</script>
<style scoped>
</style>