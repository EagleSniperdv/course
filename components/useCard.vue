<template>
  <div v-if="user">
    <img :src="profile" alt="" />
    <div class="text-right">
      <div class="">{{ name }}</div>
      <button>Log-Out</button>
    </div>
  </div>
</template>

<style scoped></style>

<script lang="ts" setup>
const user = useSupabaseUser();

const name = computed(() => user?.value.user_metadata.full_name);

const profile = computed(() => user?.value.user_metadata.avatar_url);
</script>
