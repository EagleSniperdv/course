<template>
  <div class="wrapper">
    <h1>Log in to {{ title }}</h1>
    <button>login with github</button>
  </div>
</template>

<script setup>
const { title } = useCourse();
</script>
