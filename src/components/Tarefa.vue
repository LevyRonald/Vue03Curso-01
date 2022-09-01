<template>
  <box-app>
    <div class="columns">
      <div class="column is-7">
        {{ tarefa.descricao || 'Tarefa sem descrição' }}
      </div>
      <div class="column">
        <cronometro-formulario :tempoEmSegundos="tarefa.duracaoEmSegundos" />
      </div>
    </div>
  </box-app>
</template>
<script lang="ts">
import ITarefa from "@/interfaces/ITarefa";
import BoxApp from "./Box.vue";
import { defineComponent, PropType } from "vue";
import CronometroFormulario from "./Cronometro.vue";

export default defineComponent({
  name: "TarefaApp",
  components: {
    CronometroFormulario,
    BoxApp
  },
  props: {
    tarefa: {
      type: Object as PropType<ITarefa>,
      required: true,
    },
  },
});
</script>
<style scoped>
  
</style>
