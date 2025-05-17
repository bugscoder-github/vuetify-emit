<template>
  <v-btn @click="handleClick">Parent - Update Component Two</v-btn>
  <HeaderLayout @clicked="updateValue"/>
  <SidebarLayout v-model="sharedValue"/>
</template>

<script lang="ts" setup>
import { ref } from 'vue'

const sharedValue = ref('')

function updateValue(newValue) {
  sharedValue.value = sharedValue.value == 'New value from Component One' ? 'Default' : newValue
}

function handleClick() {
  sharedValue.value = sharedValue.value == 'New value from Parent' ? 'Default' : 'New value from Parent'
}
</script>
