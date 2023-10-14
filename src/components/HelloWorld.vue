<script setup lang="ts" generic="T">
import type { Foo } from './hello'
const props = defineProps<{
  msg: string,
  data: Foo,
  bar: T
}>()

const list = [{ name: 'foo', age: 12 }]

console.log(typeof props.bar);

defineExpose({ list })

</script>

<template>
  <div class="greetings">
    <h1 class="green">{{ msg }}</h1>
    <h3>
      You’ve successfully created a project with
      <a target="_blank" href="https://vitejs.dev/">Vite</a> +
      <a target="_blank" href="https://v2.vuejs.org/">Vue 2</a>. What's next?
    </h3>
    <div v-for="item in list" :key="item.name">{{ item.name }}</div>
    <pre>{{ data }}</pre>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    display: block;
    text-align: left;
  }
}
</style>
