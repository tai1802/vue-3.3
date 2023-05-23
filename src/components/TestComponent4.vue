<script setup lang="ts">
const slot = defineSlots<{
  default?: (props: { msg: string }) => any
  item?: (props: { id: number }) => any
}>()
</script>

<template>
  <div>{{ slot.item }}</div>
</template>
