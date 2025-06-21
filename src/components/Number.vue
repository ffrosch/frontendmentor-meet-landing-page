<script setup lang="ts">
defineProps<{
    value: number;
}>();
</script>

<template>
    <div class="flex flex-col items-center">
        <div class="border-slate-300 text-slate-600 h-5xl border-s-2"></div>
        <div
            class="font-black text-s leading-m rounded-full border-2 border-slate-300 text-slate-600 w-2xl h-2xl flex items-center justify-center">
            {{ String(value).length === 1 ? `0${value}` : value }}
        </div>
    </div>
</template>

<style scoped></style>