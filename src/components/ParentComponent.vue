<script setup>
import { ref } from 'vue';
import ChildComponent from './ChildComponent.vue';
const parentMessage = ref("Hello from ParentComponent");
const emittedMessage = ref("");

const handleMessageEmitted = (msg) => {
  emittedMessage.value = msg;
};
</script>


<template>
  <div class="bg-gray-200 p-6">
    <h1 class="text-2xl mb-4">Parent Component</h1>
    <ChildComponent :message="parentMessage" @messageEmitted="handleMessageEmitted" />
    <p class="mt-4">Message from ChildComponent: <span class="text-purple-900 font-semibold">{{ emittedMessage }}</span>
    </p>
  </div>
</template>

