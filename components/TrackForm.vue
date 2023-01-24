

<script setup>

    let formName = ref("")

</script>

<template>

    <form>
        <label>Name:</label>
        <input type="text" v-model="formName">

        <label>Description:</label>
        <input type="text" v-model="formName">

        <label>Repeat:</label>
        <NumberInput class="number-input"/>

    </form>

</template>

<style lang="scss">
    form {
        display: flex;
        flex-direction: column;
        padding-top: 2em;
        padding-bottom: 2em;
        
        label {
            color: white;
            font-size: 24px;
        }

        input, button[type=button] {
            margin-top: 1em;
            margin-bottom: 1em;
            border: none;
            background-color: transparent;
            font-size: 16px;
            border-bottom: solid 2px white;
            color: white;
        }

        input:focus {
            outline: none;
        }
    }
</style>