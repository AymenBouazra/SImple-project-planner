<template>
    <nav class="filter-nav">
        <button @click="updateFilter('all')" :class="{ active: filter === 'all' }">View All</button>
        <button @click="updateFilter('completed')" :class="{ active: filter === 'completed' }">Completed</button>
        <button @click="updateFilter('ongoing')" :class="{ active: filter === 'ongoing' }">Ongoing</button>
    </nav>
</template>
<script>
export default {
    props: ['filter'],
    methods: {
        updateFilter(by) {
            this.$emit('updateFilter', by)
        }
    }
}
</script>
<style>
.filter-nav button {
    background: none;
    border: none;
    color: #bbb;
    outline: none;
    font-size: 12px;
    text-transform: uppercase;
    margin-right: 10px;
    letter-spacing: 1px;
    font-weight: bold;
    cursor: pointer;
}

.filter-nav button.active {
    color: #444;
    font-size: 14px;
}
</style>