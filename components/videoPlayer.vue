
<template>
  <iframe
    width="560"
    height="315"
    frameborder="0"
    src="https://www.youtube.com/results?search_query=chrome+dev+tools";
    allowfullscreen></iframe>
</template>

<style scoped>
  iframe {
    width: 90%;
    height: 100%;
    border-radius: 10px;
  }
</style>

<script setup>
  const props = defineProps({
    videoId: {
      type: Number,
      requuired: true,
    },
  });
</script>

