<template>
    <div>
        <img :src="response.details.ext_1.url" width="300">
        <div>{{ response.details.ext_2 }}</div>
        <div>{{ response.details.ext_3 }}</div>

        <div v-for="n in response.details.ext_4" :key="n.slag">
            <img :src="n.ext_4.url" width="400">
            <div>{{ n.ext_3 }}</div>
            <div>{{ n.ext_5 }}</div>
            <div>{{ n.ext_6 }}</div>
        </div>
    </div>
</template>

<script setup>
const config = useRuntimeConfig();

const { data: response } = await useFetch(
    `${config.public.apiBase}/rcms-api/3/service/3`,
    {
        credentials: 'include',
    }
);
</script>