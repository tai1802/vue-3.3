<!-- BEFORE -->
<!-- <script setup lang="ts">
const props = defineProps(['modelValue'])
const emit = defineEmits(['update:modelValue'])
console.log(props.modelValue)

function onInput(e: any) {
  emit('update:modelValue', e.target.value)
}
</script> -->

<!-- <template>
  <input :value="modelValue" @input="onInput" />
</template> -->

<!-- AFTER -->
<script setup lang="ts" generic="T">
const modelValue = defineModel<{
  name: string
  age: number
}>({ local: true, default: { name: 'default', age: 0 } })
</script>

<template>
  <div>inside:: {{ modelValue }}</div>
  <div style="display: flex; flex-direction: column; gap: 1rem">
    <input v-model="modelValue.name" />
    <input v-model="modelValue.age" type="number" />
  </div>
</template>
