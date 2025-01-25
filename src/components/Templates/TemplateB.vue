<template>
  <BaseTemplate>
    <template #header>
      <h1 :class="$style.header">{{ data.title }}</h1>
    </template>
    <template #body>
      <p :class="$style.body">{{ data.message }}</p>
    </template>
    <template #footer>
      <span :class="$style.footer">{{ data.date }}</span>
    </template>
  </BaseTemplate>
</template>

<script setup>
import BaseTemplate from "@/components/Base/BaseTemplate.vue"
const props = defineProps({
  data: {
    type: Object,
    required: true,
  },
});
</script>

<style lang="postcss" module>
.header {
  @apply text-blue-600 font-sans text-3xl uppercase;
}

.body {
  @apply text-gray-700 font-serif text-base leading-relaxed;
}

.footer {
  @apply text-gray-500 text-xs tracking-wide;
}
</style>
