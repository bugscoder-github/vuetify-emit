<template>
  <v-btn @click="handleClick">Component - Update Component Two</v-btn>
</template>

<script setup>
import { defineEmits } from 'vue'

const emit = defineEmits(['clicked'])

function handleClick() {
  emit('clicked', 'New value from Component One')
}
</script>