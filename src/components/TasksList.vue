<template>
    <ul class="tasks-list">
        <one-task v-for="task in tasks" :text="task.text" :id="task.id" :key="task.id" :is-important="task.isImportant"></one-task>
    </ul>
</template>
<script>
import OneTask from './OneTask.vue';

export default {
    name: 'TasksList',
    components: { OneTask },

    props: {
        tasks: {
            type: Array,
            required: true
        }
    }
}
</script>
<style>
.tasks-list {
    display: grid;
    grid-template-columns: repeat(1, 1fr);
    grid-gap: 60px 30px;
    width: 90%;
    max-width: 1200px;
    padding: 0 0 50px 0;
    list-style: none;
}

@media (min-width: 768px) {
    .tasks-list {
        grid-template-columns: repeat(2, 1fr);
    }
}
</style>