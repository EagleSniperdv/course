<template>
    <header class="header">
        <h1>
            Course:
            <span>Mastering Nuxt</span>
        </h1>
    </header>

    <div class="container">

        <div class="chapters">
            
                <h3>Chapters</h3>
            

        </div>

        <div class="lesson">
            <NuxtPage/>
        </div>
    </div>
</template>

<style scoped>
.header {
    display: flex;
    justify-content: center;
    height: 10vh;
    font-weight: lighter;
    color: blue;
}
.header h1 span {
    font-weight: bolder;
    color: white;
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
    background: rgba(54, 54, 46, 0.2);
    min-width: 20ch;
    margin-right: 4px;
    padding: 8px;
    display: flex;
    justify-content: center;
    border-radius: 10px;
}
.container .lesson {
    min-width: 65ch;
    width: 240px;
    background: yellowgreen;
    border-radius: 10px;
}


</style>