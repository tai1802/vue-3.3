<script setup lang="ts" generic="T">
defineProps<{
  items: T[]
  selected: T
}>()
</script>

<template>
  <div>
    <div>{{ items }}</div>
    <div>{{ selected }}</div>
  </div>
</template>
