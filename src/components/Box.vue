<template>
  <div class="box has-text-weight-bold">
    <slot/>
  </div>
</template>
<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: 'BoxApp'
});
</script>
<style scoped>
.box {
  background: #faf0ca;
}
</style>