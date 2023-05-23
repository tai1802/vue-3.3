<script setup lang="ts" generic="T extends string | number, U extends Item">
export interface Item {
  id: string | number
  label: string
  name: string
}
defineProps<{
  id: T
  list: U[]
}>()

// BEFORE
// const emit = defineEmits<{
//   (e: 'foo', id: number): void
//   (e: 'bar', name: string, ...rest: any[]): void
// }>()

// AFTER
const emit = defineEmits<{
  foo: [id: number]
  bar: [name: string, ...rest: any[]]
}>()
</script>

<template>
  <div>
    <button @click="() => emit('foo', 123)">Click</button>
    <button @click="() => emit('bar', 'test', 'test2', 'test3')">Click2</button>
  </div>
</template>
