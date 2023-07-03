<template>
<div>
    {{JSON.stringify(testData)}}
</div>
</template>
<script setup lang="ts">
import mockData from '../assets/mockData'
// Props
const props = defineProps({
    data: {
        type: Object, // Do TS type later once I've created function that formats the data
        required: true,
    }
})

// Data formatting 
const DAY_INDEXES = {
    0: 'Sun',
    1: 'Mon',
    2: 'Tue',
    3: 'Wed',
    4: 'Thu',
    5: 'Fri',
    6: 'Sat',
}

const formatData = (chartData) => {
    return chartData.reduce((dates, dateString) => {
        const date = new Date(dateString);
        const day = DAY_INDEXES[date.getDay()];

        (dates[day] = dates[day] || []).push(date) 

        return dates;
    }, {})
}

const testData = formatData(mockData.map(item => item.date))

</script>
<style scoped lang="scss">
</style>