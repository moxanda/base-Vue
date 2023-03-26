<template>
  <h1> ComponenteHijo {{mensaje}} <h1> {{param1}} </h1> </h1>
</template>
<script setup lang='ts'>
  // import { ref } from 'vue'
  // let mensaje = ref('Prueba')
  let mensaje = 'PruebA'
  defineProps({ param1: String, param2: String })
/*  props: {
  menmen: String
}
*/
</script>