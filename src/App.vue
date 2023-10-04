<template>
    <div class="p-8 bg-gray-100 min-h-screen">
        <DataTable :tasks="tasks" />
    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import DataTable from './components/DataTable.vue';

const tasks = ref([]);

const fetchTasks = async () => {
    const response = await fetch('http://localhost:3000/tasks');
    tasks.value = await response.json();
    console.log(tasks.value);
}

onMounted(() => {
    fetchTasks();
});
</script>
