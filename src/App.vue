<script setup lang="ts">
import { ref } from 'vue'
// import TestComponent1 from './components/TestComponent1.vue'
// import TestComponent2 from './components/TestComponent2.vue'
// import TestComponent3 from './components/TestComponent3.vue'
// import TestComponent4 from './components/TestComponent4.vue'
// import TestComponent5 from './components/TestComponent5.vue'
import TestComponent6 from './components/TestComponent6.vue'
import TestComponent7 from './components/TestComponent7.vue'

const data = ref({
  name: '',
  age: 26
})
const handleGetFoo = (value: any) => {
  console.log(value)
}

const handleGetBar = (...value: any[]) => {
  console.log(value)
}
</script>

<template>
  <main>
    <div>{{ data }}</div>
    <!-- <TestComponent1 label="label" name="name" extra-prop="" /> -->
    <!-- <TestComponent2 :items="[123]" :selected="12" /> -->
    <!-- <TestComponent3
      :list="[{ id: 12, label: 'label', name: 'name' }]"
      id="12"
      @foo="handleGetFoo"
      @bar="handleGetBar"
    /> -->
    <!-- <TestComponent4>
      <div>ABC</div>
      <template #item>ABCDÂDaaa</template>
    </TestComponent4> -->
    <!-- <TestComponent5 msg="tttt" /> -->
    <TestComponent6 v-model="data" />
    <TestComponent7 foo="123" />
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
