<script setup lang="ts">
import { watchEffect } from 'vue'

const { msg = 'hello' } = defineProps(['msg'])

watchEffect(() => {
  // accessing `msg` in watchers and computed getters
  // tracks it as a dependency, just like accessing `props.msg`
  console.log(`msg is: ${msg}`)
})
</script>

<template>{{ msg }}</template>
