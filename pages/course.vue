<template>
  <div></div>
  <header class="header">
    <h1>
      Course:
      <span>{{ title }}</span>
    </h1>
    <userCard />
  </header>

  <div class="container">
    <div class="chapters">
      <h3>Chapters</h3>
      <div class="chapter_item" v-for="chapter in chapters" :key="chapter.slug">
        <h4>{{ chapter.title }}</h4>
        <NuxtLink
          v-for="(lesson, index) in chapter.lessons"
          :key="lesson.slug"
          :to="lesson.path"
          external
        >
          <span>{{ index + 1 }}</span>
          {{ lesson.title }}
        </NuxtLink>
      </div>
    </div>

    <div class="lesson">
      <NuxtErrorBoundary>
        <NuxtPage />
        <template #error="{ error }">
          <p>
            oh no, something broke!
            <code>{{ error }}</code>
          </p>
          <p>
            <button @click="resetError(error)">Reset</button>
          </p>
        </template>
      </NuxtErrorBoundary>
    </div>
  </div>
</template>

<style scoped>
.header {
  display: flex;
  justify-content: center;
  height: 10vh;
  font-weight: lighter;
  color: rgb(255, 255, 255);
}
.header h1 span {
  font-weight: bolder;
  color: rgb(243, 16, 16);
}
.container {
  width: 100%;
  height: 90vh;
  display: flex;
  justify-content: center;
  /* align-items: center; */
  column-gap: 10px;
}
.container .chapters {
  background: rgba(243, 243, 241, 0.7);
  min-width: 20ch;
  height: 100%;
  margin-right: 4px;
  padding: 8px;
  display: flex;
  flex-direction: column;
  /* justify-content: center; */
  border-radius: 10px;
  margin: 15px;
}
.chapters h4 {
  padding: 15px;
}
.chapters .chapter_item {
  display: flex;
  flex-direction: column;
}
.container .lesson {
  min-width: 65ch;
  width: 240px;
  background: yellowgreen;
  border-radius: 10px;
}
.router-link-active {
  color: yellow;
}
</style>

<script setup>
const { chapters, title } = useCourse();
// const title = computed(() => {
//     return
// });

const resetError = async (error) => {
  await navigateTo(
    'http://localhost:3000/course/chapter/1-chapter-1/lesson/1-introduction-typescript',
    { external: true }
  );
  error.value = null;
};

useHead({
  title: 'new title',
});

// definePageMeta({
//     layout,
// })
</script>
