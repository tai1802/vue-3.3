<script setup lang="ts">
defineSlots<{
  default?: (props: { msg: string }) => any
  item?: (props: { id: number }) => any
}>()
</script>

<template>
  <div>
    <slot msg="hi there"></slot>
  </div>
</template>
