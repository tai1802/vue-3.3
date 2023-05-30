<script setup lang="ts">
import { ref } from 'vue'
import Switch from './components/Switch.vue'
import LocalFalse from './components/TestComponent6A.vue'
import LocalTrue from './components/TestComponent6B.vue'

const data = ref({
  name: '',
  age: 26
})

const defineModelLocal = ref(false)
const passProps = ref(false)
</script>

<template>
  <main>
    <div>isLocal: {{ defineModelLocal }}</div>
    <Switch v-model="defineModelLocal" />
    <div v-if="defineModelLocal">
      <div>passProps: {{ passProps }}</div>
      <Switch v-model="passProps" />
      <div>outside: {{ data }}</div>
      <template v-if="passProps">
        <LocalTrue v-model="data" />
      </template>
      <template v-else>
        <LocalTrue />
      </template>
    </div>
    <div v-else>
      <div>passProps: {{ passProps }}</div>
      <Switch v-model="passProps" />
      <div>outside: {{ data }}</div>
      <template v-if="passProps">
        <LocalFalse v-model="data" />
      </template>
      <template v-else>
        <LocalFalse />
      </template>
    </div>
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
