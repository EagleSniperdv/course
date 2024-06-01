<template>
  <NuxtLink :href="firstLesson.path" external>Go to first Lesson</NuxtLink>
</template>

<script lang="ts" setup>
const firstLesson = useFirstLesson();
</script>
