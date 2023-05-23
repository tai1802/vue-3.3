<script setup lang="ts">
import { ref, toRef, toValue, unref, computed, watch } from 'vue'
import type { MaybeRefOrGetter } from 'vue'

// defineOptions({ inheritAttrs: false })
const props = defineProps<{ foo: string }>()
// const existingRef = ref(123)

function useFeature(id: MaybeRefOrGetter<number | string>) {
  watch(
    () => toValue(id),
    (id) => {
      // react to id changes
      console.log(id)
    },
    { immediate: true }
  )
}

// equivalent to ref(1)
// console.log(toRef(1))
// creates a readonly ref that calls the getter on .value access
// console.log(toRef(() => props.foo))
const myRef = toRef(() => props.foo)
const foo = computed(() => props.foo)
// console.log(myRef)
// console.log(toValue(() => props.foo))
// returns existing refs as-is
// console.log(toRef(existingRef))

// console.log(toValue(1)) //       --> 1
// console.log(toValue(ref(1))) //  --> 1
// console.log(toValue(() => 1)) // --> 1
// console.log(unref(toRef(1)))

// useFeature(1)
// useFeature(ref(1))
// useFeature(() => 1)

// before: allocating unnecessary intermediate refs
useFeature(computed(() => props.foo))
useFeature(toRef(props, 'foo'))

// after: more efficient and succinct
useFeature(() => props.foo)
</script>

<template>
  <div></div>
</template>
