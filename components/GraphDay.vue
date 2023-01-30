
<script>

    export default {
        props: ['dayData', 'roundedLeft', 'roundedRight'],
    }

</script>


<template>

    <div  class="graph-day">
        <p>{{ dayData.name }}</p>
        <div 
            :style="{'height': `${dayData.value}px`, 'background-color': 'gold', 'width': '32px'}"
            :class="roundedLeft ? 'rounded-left' : roundedRight ? 'rounded-right' : ''"
        />
    </div>

</template>

<style lang="scss" scoped>

    .graph-day {
        height: 128px;
        width: 32px;
        display: flex;
        flex-direction: column;

        p {
            position: relative;
            bottom: 1em;
            border-bottom: 2px solid white;
            width: 32px;
            text-align: center;
        }

        div {
            position: relative;
            bottom: -0.3em;
        }

        .rounded-left {
            border-bottom-left-radius: 6px;
        }

        .rounded-right {
            border-bottom-right-radius: 6px;
        }
    }

</style>