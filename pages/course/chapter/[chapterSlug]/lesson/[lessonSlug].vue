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



console.log(course);

</script>