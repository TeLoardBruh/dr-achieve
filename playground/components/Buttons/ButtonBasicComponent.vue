<template>
  <div>
    <div
      type="button"
      class="border border-gray-200 bg-gray-200 text-gray-700 rounded-md px-2 py-2"
      :class="className"
    >
      <slot name="icon" />
      <p class="font-semibold text-btn">
        {{ text }}
      </p>
    </div>
  </div>
</template>

<script setup lang="ts">
defineProps<{
  text: string;
  className?: string;
}>();
</script>

<style scoped>
.text-btn {
  /* color: #505050; */
}
</style>
