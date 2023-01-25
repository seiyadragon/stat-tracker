
<script>

    export default {
        props: {
            label: String,
            canTick: Boolean,
            valueID: Number
        },
        data() {
            return {
                checkboxTicked: false
            }
        }
    }

</script>

<template>

    <div :class="checkboxTicked && canTick ? 'selected-input' : 'unselected-input'" @click="canTick ? $refs.checkInput.click() : checkboxTicked = false">
        <input type="checkbox" v-model="checkboxTicked" @click="$emit('checkbox-clicked', [valueID, !checkboxTicked])" ref="checkInput">
        <label>{{ label }}</label>
    </div>

</template>

<style lang="scss" scoped>

    div {
        background-color: rgb(98+32, 74+32, 46+32);
        padding-left: 10px;
        padding-right: 10px;
        margin-top: 1em;
        margin-bottom: 1em;

        label {
            font-size: 20px;
        }

        input {
            display: none;
        }

        .selected-input {
            border: 2px solid gold;
        }

        .unselected-input {
            border: 2px solid rgb(98+32, 74+32, 46+32);
        }
    }

</style>