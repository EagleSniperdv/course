<template>
<label for="input"
:class="modelValue ? 'bg-green-500' : 'bg-gray-500'"
>
<input type="checkbox"
    :value="modelValue"
    @input="() => $emit('update:modelValue',!modelValue)"
    class="hidden"
>
{{ modelValue ? 'completed!' : 'Mark as complete' }}
</label>
</template>

<style scoped>

label {
  border-radius: 10px;
  padding: 5px;
  margin: 10px;
}
::selection {
  display: none;
}

.bg-green-500 {
  background-color: #10b981; /* Equivalent to bg-green-500 in Tailwind */
}

.bg-gray-500 {
  background-color: #6b7280;
}
</style>

<script setup>
defineProps({
  modelValue: {
    type: Boolean,
    default:false
  },
});

defineEmits(['update:modelValue']);
</script>

