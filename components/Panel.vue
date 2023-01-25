

<template>

    <div class="outer">
        <div class="inner">
            <slot />
        </div>
    </div>

</template>

<style lang="scss" scoped>

    .outer {
        padding-left: 384px;
        padding-right: 384px;

        @media (max-width: 400px) {
            padding-left: 24px;
            padding-right: 24px;
        }

        padding-top: 24px;
        padding-bottom: 24px;
        .inner {
    
            border-top: 4px solid gold;
            border-bottom: 4px solid gold;

            background-color: rgb(98, 74, 46, 0.5);
            backdrop-filter: blur(3px);
        }
    }


</style>