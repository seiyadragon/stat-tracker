

<script>

    export default {
        data() {
            return {
                weekData: {
                    monday: {
                        name: 'Mon',
                        value: 16,
                    },
                    tuesday: {
                        name: 'Tue',
                        value: 32,
                    },
                    wednesday: {
                        name: 'Wed',
                        value: 4,
                    },
                    thursday: {
                        name: 'Thr',
                        value: 6,
                    },
                    friday: {
                        name: 'Fri',
                        value: 100,
                    },
                    saturday: {
                        name: 'Sat',
                        value: 23,
                    },
                    sunday: {
                        name: 'Sun',
                        value: 64,
                    }
                }
            }
        }
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
        height: 128px;
        border-bottom-left-radius: 20px;
        border-bottom-right-radius: 20px;
        display: flex;
        flex-direction: row;
        justify-content: space-between;
    }

</style>