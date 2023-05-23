<script setup lang="ts">
interface Props {
  label: string
  name: string
}

// imported + intersection type
defineProps<Props & { extraProp?: string }>()
</script>

<template>
  <div></div>
</template>
