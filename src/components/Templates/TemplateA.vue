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
  @apply text-red-500 font-serif text-3xl;
}

.body {
  @apply text-gray-800 font-sans text-lg;
}

.footer {
  @apply text-gray-600 text-sm italic;
}
</style>
