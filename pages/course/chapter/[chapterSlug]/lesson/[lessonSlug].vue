<template>
    <div class="container">
        <h2>lesson</h2>
        <p>This is a lesson</p>
        <p>{{ chapter.title  }}</p>
        <p>{{ lesson.title }}</p>
        <videoPlayer 
            v-if="lesson.videoId"
            :videoId="lesson.videoId"
        />
        <!-- <LessonCompleteButton 
        :model-value="isLessonComplete"
        @update:model-value="toggleComplete"
        /> -->
        <LessonCompleteButton 
        :model-value="isLessonComplete"
        @update:model-value="
        throw createError('could not Update');
        "
        />
        <p>{{lesson.text}}</p>
    </div>
</template>



<style scoped>
    .container {
        margin: 5px;
        padding: 5px;
        box-sizing: border-box;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

    }

    .container h2,p {
        margin-bottom: 10px;
    }
</style>


<script setup>
import LessonCompleteButton from '~/components/LessonCompleteButton.client.vue';



const course = useCourse();
const route = useRoute();

const chapter = computed(() => {
    return course.chapters.find(
        (chapter) => chapter.slug === route.params.chapterSlug
    );
});

const lesson = computed(() => {
    return chapter.value.lessons.find(
        (lesson) => lesson.slug === route.params.lessonSlug
    );
});

const title = computed(() => {
    return `${lesson.value.title} - ${course.title}`
})

useHead({
    title,
})

const progress = useLocalStorage('progress', []);

const isLessonComplete = computed(() => {
    if (!progress.value[chapter.value.number - 1]) {
        return false;
    }

    if (!progress.value[chapter.value.number - 1][lesson.value.number - 1]) {
        return false;
    }

    return progress.value[chapter.value.number - 1][lesson.value.number - 1]
});

const toggleComplete = () => {
    if (!progress.value[chapter.value.number - 1]) {
        progress.value[chapter.value.number - 1] = [];
    }

    progress.value[chapter.value.number - 1][lesson.value.number - 1] = !isLessonComplete.value;
}

</script>