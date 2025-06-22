<script setup lang="ts">
defineProps<{
  value: number;
}>();
</script>

<template>
  <div class="flex flex-col items-center">
    <div class="h-5xl border-s-2 border-slate-300 text-slate-600"></div>
    <div
      class="text-s leading-m h-2xl flex w-2xl items-center justify-center rounded-full border-2 border-slate-300 bg-white font-black text-slate-600"
    >
      {{ String(value).length === 1 ? `0${value}` : value }}
    </div>
  </div>
</template>

<style scoped></style>
