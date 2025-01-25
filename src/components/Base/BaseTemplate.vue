<template>
  <div :class="$style.card">
    <div :class="$style.header">
      <slot name="header" />
    </div>
    <div :class="$style.body">
      <slot name="body" />
    </div>
    <div :class="$style.footer">
      <slot name="footer" />
    </div>
  </div>
</template>


<script setup>

</script>

<style lang="postcss" module>
.card {
  @apply p-5 rounded-lg max-w-md mx-auto bg-white shadow-md;
}

.header {
  @apply text-center text-2xl font-bold mb-4;
}

.body {
  @apply text-center text-lg mb-6;
}

.footer {
  @apply text-center text-sm text-gray-500;
}
</style>
