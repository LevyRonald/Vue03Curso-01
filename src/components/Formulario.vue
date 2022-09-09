<template>
  <div class="box formulario">
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
        <temporizador-formulario @aoTemporizadorFinalizado="finalizarTarefa" />
      </div>
    </div>
  </div>
</template>
<script lang="ts">
import TemporizadorFormulario from "./Temporizador.vue";
import { defineComponent } from "vue";

export default defineComponent({
  name: "FormularioApp",
  emits: ['aoSalvarTarefa'],
  components: { TemporizadorFormulario },
  data() {
    return {
      descricao: "",
    };
  },
  methods: {
    finalizarTarefa(tempoDecorrido: number): void {
      this.$emit('aoSalvarTarefa', {
        duracaoEmSegundos: tempoDecorrido,
        descricao: this.descricao
      })
      this.descricao = "";
    },
  },
});
</script>
<style>
.formulario {
  color: var(--texto-primario);
  background-color: var(--bg-primario);
}
</style>