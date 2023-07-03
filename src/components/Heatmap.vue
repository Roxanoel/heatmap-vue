<template>
<div>

</div>
</template>
<script setup lang="ts">
import { defineProps } from 'vue';

const props = defineProps({
    data: {
        type: Object, // Do TS type later once I've created function that formats the data
        required: true,
    }
})
</script>
<style scoped lang="scss">
</style>