<template>
  <div :class="$style.app">
    <div :class="$style.container">
      <!-- App Header -->
      <header :class="$style.header">
        <h1 :class="$style.title">Digital Wedding Invitations</h1>
        <p :class="$style.subtitle">Select a design template and preview your invitation</p>
      </header>

      <!-- Template Selector -->
      <div :class="$style.templateSelector">
        <label for="template" :class="$style.label">Choose Your Template</label>
        <select id="template" v-model="selectedTemplate" :class="$style.dropdown">
          <option value="TemplateA">Elegant Red (Template A)</option>
          <option value="TemplateB">Modern Blue (Template B)</option>
        </select>
      </div>

      <!-- Invitation Preview -->
      <h2 :class="$style.previewTitle">Invitation Preview</h2>
      <component :is="currentTemplate" :data="invitationData" />
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';
import TemplateA from './components/Templates/TemplateA.vue';
import TemplateB from './components/Templates/TemplateB.vue';

// Dynamic template selection
const selectedTemplate = ref('TemplateA');

// Data to pass to the templates
const invitationData = {
  title: "You're Invited!",
  message: 'Please join us for our special day.',
  date: 'January 1, 2025',
};

// Map templates to components for dynamic rendering
const templates = {
  TemplateA,
  TemplateB,
};

// Dynamically get the selected template
const currentTemplate = computed(() => templates[selectedTemplate.value]);
</script>

<style lang="postcss" module>
.app {
  @apply h-dvh min-w-full overflow-y-hidden flex flex-col justify-center items-center;
}

.container {
  @apply w-full max-w-4xl bg-white p-8 rounded-2xl;
}

.header {
  @apply text-center mb-8;
}

.title {
  @apply text-3xl font-bold text-gray-800 tracking-tight mb-2;
}

.subtitle {
  @apply text-gray-600 text-sm;
}

.templateSelector {
  @apply flex flex-col mb-8;
}

.label {
  @apply block text-lg font-medium text-gray-700 mb-2;
}

.dropdown {
  @apply w-full bg-gray-50 border border-gray-300 text-gray-700 text-sm rounded-lg shadow-sm focus:ring-blue-500 focus:border-blue-500 p-3;
}

.previewContainer {
  @apply mt-6;
}

.previewTitle {
  @apply text-2xl font-semibold text-gray-800 mb-4;
}

.preview {
  @apply bg-white p-8 rounded-xl shadow-lg border border-gray-200;
}
</style>
