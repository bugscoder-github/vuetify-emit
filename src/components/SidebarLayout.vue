<!-- ComponentTwo.vue -->
<template>
  <v-text-field v-model="displayValue" />
</template>

<script setup>
const DEFAULT_VALUE = 'Default value from ComponentTwo'

const model = defineModel('modelValue', {
  type: String,
  default: DEFAULT_VALUE
})

const displayValue = computed({
  get() {
    return model.value || DEFAULT_VALUE
  },
  set(value) {
    model.value = value
  }
})
</script>