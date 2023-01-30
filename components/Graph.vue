

<script>

    export default {
        props: ['weekData'],
    }

</script>

<template>

    <div>
        <GraphDay :day-data="weekData.monday" :rounded-left="true"/>
        <GraphDay :day-data="weekData.tuesday"/>
        <GraphDay :day-data="weekData.wednesday"/>
        <GraphDay :day-data="weekData.thursday"/>
        <GraphDay :day-data="weekData.friday"/>
        <GraphDay :day-data="weekData.saturday"/>
        <GraphDay :day-data="weekData.sunday" :rounded-right="true"/>
    </div>

</template>

<style lang="scss" scoped>

    div {
        min-height: 50%;
        max-height: 50%;
        border-bottom-left-radius: 20px;
        border-bottom-right-radius: 20px;
        display: flex;
        flex-direction: row;
        justify-content: space-between;
    }

</style>