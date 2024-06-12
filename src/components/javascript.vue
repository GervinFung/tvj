<script setup>
import { defineProps } from "vue";

const props = defineProps({
  message: {
    type: String,
    default: "Hello I am a JS component!",
  },
  variant: {
    type: String,
    validator: (variant) => ["primary", "secondary"].includes(variant),
  },
});

const emit = defineEmits(["bombastic"]);
</script>

<template>
  <h1>{{ props.message }}</h1>
  <button
    @click="
      emit('bombastic', {
        hello: 'it is me',
      })
    "
  >
    Click me
  </button>
</template>
