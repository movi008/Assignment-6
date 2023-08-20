<template>
  <div class="bg-white p-4 shadow-md rounded-md">
    <p>Received message from ParentComponent: <span class="text-purple-900 font-semibold">{{ message }}</span></p>
    <button class="mt-2 px-4 py-2 bg-blue-500 text-white rounded" @click="emitCustomMessage">Emit Message</button>
  </div>
</template>
  
<script setup>
import { defineProps, defineEmits } from 'vue';

const props = defineProps({
  message: {
    type: String,
    required: true,
  }
})
const emits = defineEmits(['messageEmitted'])

const emitCustomMessage = () => {
  emits('messageEmitted', 'Custom message from ChildComponent');
};
</script>