<script setup>
import ComponentA from "./ComponentA.vue";
import ComponentB from "./ComponentB.vue";
import { ref } from "vue";

const currentComponentName = ref("ComponentA");

const components = {
  ComponentA,
  ComponentB,
};

const toggleCurrentComponent = () => {
  currentComponentName.value =
    currentComponentName.value == "ComponentA" ? "ComponentB" : "ComponentA";
};
</script>

<template>
  <div>
    <component :is="components[currentComponentName]"></component>
    <button @click="toggleCurrentComponent">Toggle</button>
  </div>
</template> 