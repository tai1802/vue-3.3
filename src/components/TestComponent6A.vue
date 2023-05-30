<script setup lang="ts" generic="T">
const modelValue = defineModel<{
  name: string
  age: number
}>({ local: false, default: { name: 'default', age: 0 } })
</script>

<template>
  <div>inside:: {{ modelValue }}</div>
  <div style="display: flex; flex-direction: column; gap: 1rem">
    <input v-model="modelValue.name" />
    <input v-model="modelValue.age" type="number" />
  </div>
</template>
