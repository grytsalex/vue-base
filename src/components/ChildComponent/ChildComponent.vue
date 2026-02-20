<script setup lang="ts">
const props = defineProps<{
  childProps: {
    prop1: string;
    prop2: string;
  };
}>();

const emit = defineEmits<{
  (e: "update:changeParentWithEmit"): void;
}>();

const changeParent = () => {
  emit("update:changeParentWithEmit");
};

console.log("childProps", props.childProps);

</script>

<template>
  <div
    style="
      display: flex;
      align-items: center;
      justify-content: space-between;
      background-color: #f0f0f0;
      padding: 10px;
      border-radius: 5px;
      gap: 20px;
      color: blue;
    "
  >
    <span style="color: red;">{{ childProps.prop1 }}</span>
    <span style="color: green;">{{ childProps.prop2 }}</span>
    <button @click="changeParent" style="padding: 10px; background-color: #ccc">
      Change parent
    </button>
  </div>
</template>

<style scoped></style>
