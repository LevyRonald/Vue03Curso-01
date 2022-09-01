<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <barra-lateral />
    </div>
    <div class="column is-three-quarter">
      <formulario-app @aoSalvarTarefa="salvarTarefa"/>
      <div class="lista">
        <tarefa-app v-for="(tarefa, index) in tarefas" :key="index" :tarefa="tarefa"/>
        <box-app v-if="listaEstaVazia">
          Você não está muito produtivo hoje
        </box-app>
      </div>
    </div>
  </main>
</template>

<script lang="ts">
import TarefaApp from "./components/Tarefa.vue";
import { defineComponent } from "vue";
import BarraLateral from "./components/BarraLateral.vue";
import FormularioApp from "./components/Formulario.vue";
import ITarefa from './interfaces/ITarefa'
import BoxApp from "./components/Box.vue";

export default defineComponent({
  name: "App",
  components: {
    BarraLateral,
    FormularioApp,
    TarefaApp,
    BoxApp
  },
  data() {
    return {
      tarefas: [] as ITarefa[]
    }
  },
  computed: {
    listaEstaVazia(): boolean {
      return this.tarefas.length === 0
    }
  },
  methods: {
    salvarTarefa (tarefa: ITarefa) {
      this.tarefas.push(tarefa)
    }
  }
});
</script> 

<style>
.lista {
  padding: 1.25rem;
}
</style>
