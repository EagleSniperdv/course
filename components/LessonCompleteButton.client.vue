<template>
<label for="input">
<input type="checkbox"
    :value="modelValue"
    @input="() => $emit('update:modelValue',!modelValue)"
    class="hidden"
>
{{ modelValue ? 'completed!' : 'Mark as complete' }}
</label>
</template>

<style scoped>
::selection {
  display: none;
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

