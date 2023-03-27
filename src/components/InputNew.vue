<template>
  <form action='' @submit.prevent="handleSubmit">
    <input type='text' v-model="text" />
  </form>
  Input New
</template>
<script setup>
  import {ref, defineEmits } from 'vue'
  const text = ref('')
  const emits = defineEmits(['onNewItem'])
  function handleSubmit(){
    // alert('Entro en Comp InputNew handleSubmit')
    if (text != '') {
  
      emits('onNewItem',text)
      text.value = ''
    }
  }
</script>
<style scoped>
</style>