
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
        z-index: 98;

        .inner {
            padding-left: 384px;
            padding-right: 384px;
            
            @media (max-width: 400px) {
                padding-left: 24px;
                padding-right: 24px;
            }

            margin-top: 23vh;
            margin-bottom: 86vh;
            height: 63vh;

            background-color: rgb(98, 74, 46, 0.5);
            backdrop-filter: blur(3px);

            border-top: 4px solid gold;
            border-bottom: 4px solid gold;

            z-index: 99;

            font-family: 'Ubuntu';
        }
    }

</style>