

<script setup>

    let value = ref(0)

</script>

<template>

    <div>
        <div class="main">
            <button type="button" @click="value++">+</button>
            <input type="text" v-model="value" @change="$emit('value-change', value)">
            <button type="button" @click="value--">-</button>
        </div>
        <slot />
    </div>

</template>

<style lang="scss" scoped>

    div {
        text-align: center;

        .main {
            display: flex;
            flex-direction: row;

            input {
                width: 96.6%;
                text-align: center;
            }
        }
    }

</style>