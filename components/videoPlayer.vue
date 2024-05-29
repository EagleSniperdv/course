
<template>
  <iframe
    width="560"
    height="315"
    :src="`https://player.vimeo.com/video/${props.videoId}`"
    frameborder="0"
    allowfullscreen></iframe>
</template>

<style scoped>
  iframe {
    width: 100%;
    height: 100%;
  }
</style>

<script setup>
  const props = defineProps({
    videoId: {
      type: String,
      requuired: true,
    },
  });
</script>

