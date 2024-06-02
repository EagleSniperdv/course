<template>
  <div class="wrapper">
    <h1>Log in to {{ title }}</h1>
    <button @click="login">login with github</button>
  </div>
</template>

<script setup>
const { title } = useCourse();
const supabase = useSupabaseClient();

const login = async () => {
  const { error } = await supabase.auth.signInWithOAuth({
    provider: 'github',
  });

  if (error) {
    console.error(error);
  }
};
</script>
