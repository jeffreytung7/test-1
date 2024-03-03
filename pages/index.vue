<script setup lang="ts">

const { data, error } = await useAsyncData('test', async () => {
    if (process.server) {
        console.log('Server: hi');
    } else if (process.client) {
        console.log('Client: hi');
    }
    const response = await $fetch('/api/test')
});
</script>

<template>
    <main>
        hi
    </main>
</template>
