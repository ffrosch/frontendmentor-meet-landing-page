<script setup lang="ts">
defineProps<{
  variant: "primary" | "secondary";
}>();
</script>

<template>
  <button
    class="py-s px-xl rounded-full font-black text-nowrap text-white"
    :class="{
      'bg-primary hover:bg-primary-light focus:bg-primary-light':
        variant === 'primary',
      'bg-secondary hover:bg-secondary-light focus:bg-secondary-light':
        variant === 'secondary',
    }"
  >
    <slot>Button</slot>
  </button>
</template>
