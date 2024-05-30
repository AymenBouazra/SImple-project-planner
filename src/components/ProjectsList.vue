<template>
    <div v-for="project in projects" :key="project.id">
        <SingleProject :project="project" @delete="handleDelete" @complete="handleComplete" />
    </div>
</template>
<script>
import SingleProject from "./SingleProject.vue";
export default {
    props: ['projects'],
    name: 'ProjectsList',
    emits: ['deleteProject', 'complete'],
    components: {
        SingleProject
    },
    methods: {
        handleDelete(id) {
            this.$emit('deleteProject', id)
        },
        handleComplete(id) {
            this.$emit('complete', id)
        }
    }
}
</script>
<style></style>