

<script>

    export default {
        data() {
            return {
                value: 0
            }
        },
        methods: {
            onPlusClick() {
                this.value++
                this.$emit('value-change', [this.value])
            },
            onMinusClick() {
                this.value--
                this.$emit('value-change', [this.value])
            }
        }
    }

</script>

<template>

    <div>
        <slot />
        <div class="main">
            <button type="button" @click="onPlusClick">+</button>
            <input type="text" v-model="value" @change="$emit('value-change', [value])">
            <button type="button" @click="onMinusClick">-</button>
        </div>
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