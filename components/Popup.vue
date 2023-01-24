
<script setup>
    
</script>

<template>

    <div class="outter" @click="$emit('onBackClick')">
        <div class="inner" @click.stop>
            <slot />
        </div>
    </div>

</template>

<style lang="scss" scoped>

    .outter {
        position: fixed;
        background-color: rgb(100, 100, 100, 0.55);
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;

        .inner {
            padding-left: 24px;
            padding-right: 24px;

            margin-top: 23vh;
            margin-bottom: 66vh;
            height: 43vh;

            background-color: rgb(104, 100, 57);
        }
    }

</style>