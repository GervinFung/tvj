<script setup lang="ts">
import { defineProps } from "vue";

const props = withDefaults(
  defineProps<
    Readonly<{
      message?: string;
      variant: "primary" | "secondary";
    }>
  >(),
  {
    message: "Hello I am a TS component!",
  },
);

const emit = defineEmits<
  Readonly<{
    bombastic: [value: "!"];
  }>
>();
</script>

<template>
  <h1>{{ props.message }}</h1>
  <button @click="emit('bombastic', '!')">Click me</button>
</template>
