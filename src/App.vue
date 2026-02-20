<script setup lang="ts">
import { ref } from "vue";
import ParentComponent from "@components/ParentComponent/ParentComponent.vue";

const count = ref(0);
const spanValue = ref("Initital");
const h1Value = ref("Initital");
const pValue = ref("Initital");

const increment = () => {
  count.value++;
};

const decrement = () => {
  count.value--;
};

const reset = () => {
  count.value = 0;
};
</script>

<template>
  <header />
  <main style="display: flex; flex-direction: column; gap: 20px;">
    <div>
      <button @click="increment">Increment</button>
      <button @click="decrement">Decrement</button>
      <button @click="reset">Reset</button>
      <p>Count: {{ count }}</p>
    </div>
    <div
      style="
        margin-top: 20px;
        display: flex;
        justify-content: center;
        align-items: center;
        background-color: #f0f0f0;
        padding: 10px;
        border-radius: 5px;
        flex-direction: column;
        gap: 10px;
      "
    >
      <p style="margin-right: 10px; color: red">P tag value: {{ pValue }}</p>
      <span style="margin-right: 10px; color: blue">Span tag value: {{ spanValue }}</span>
      <h1 style="margin-right: 10px; color: green">H1 tag value: {{ h1Value }}</h1>
    </div>
  </main>
  <footer style="display: flex; justify-content: center; align-items: center; margin-top: 20px; width: 100%;">
    <ParentComponent />
  </footer>
</template>

<style scoped>
/**
 * Styles for the application.
 */
</style>
