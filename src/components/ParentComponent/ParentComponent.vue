<script setup lang="ts">
import { ref } from "vue";
import ChildComponent from "@components/ChildComponent/ChildComponent.vue";

const parrentState = ref({
  prop1: "value1",
  prop2: "value2",
});

const changeParentWithEmit = () => {
  parrentState.value.prop1 = "new value1";
  parrentState.value.prop2 = "new value2";
};

</script>

<template>
  <ChildComponent :childProps="parrentState" @update:changeParentWithEmit="changeParentWithEmit" />
</template>

<style scoped></style>
