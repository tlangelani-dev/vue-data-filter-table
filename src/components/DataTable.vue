<template>
    <div class="bg-white relative border rounded-lg">
        <table class="w-full text-sm text-left text-gray-500">
            <thead class="text-sm text-gray-700 uppercase bg-gray-50">
                <tr>
                    <th class="px-4 py-3">Id</th>
                    <th class="px-4 py-3">Assigned To</th>
                    <th class="px-4 py-3">Status</th>
                    <th class="px-4 py-3">Title</th>
                    <th class="px-4 py-3">Due</th>
                    <th class="px-4 py-3">
                        <span class="sr-only">Actions</span>
                    </th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="item in tasks" :key="item.id" class="border-b">
                    <td class="px-4 py-3 font-medium text-gray-900">{{ item.id }}</td>
                    <td class="px-4 py-3 font-medium text-gray-900">{{ item.assigned_to }}</td>
                    <td class="px-4 py-3 font-medium">{{ item.status }}</td>
                    <td class="px-4 py-3 font-medium">{{ item.title }}</td>
                    <td class="px-4 py-3 font-medium">{{ item.due_date }}</td>
                    <td class="px-4 py-3 flex items-center justify-end">
                        <a href="#" class="text-indigo-500 hover:underline">Details</a>
                    </td>
                </tr>
            </tbody>
            
        </table>
    </div>
</template>

<script setup>
defineProps({
    tasks: {
        type: Array,
        required: true,
    }
});
</script>
