<script setup lang="ts">
import TypeScript from "./components/typescript.vue";
import Javascript from "./components/javascript.vue";

const bombastic =
  (kind: "T" | "J") =>
  <S extends string>(value: S) => {
    {
      if (value === "!") {
        console.log(`Good, I am a ${kind}S component!`);
      } else {
        throw new TypeError(`Gotcha: I am actually ${value}`);
      }
    }
  };
</script>

<template>
  <TypeScript @bombastic="bombastic('T')" variant="primary" />
  <Javascript @bombastic="bombastic('J')" variant="no way" />
</template>
