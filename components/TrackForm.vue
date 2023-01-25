

<script setup>

    let formName = ref("")

</script>

<template>

    <form>
        <label>Name:</label>
        <input type="text" v-model="formName">

        <label>Question:</label>
        <input type="text" v-model="formName">

        <label>Repeat:</label>
        <NumberInput>
            <label class="number-input-label">Days</label>
        </NumberInput>

        <label>Answer Type:</label>
        <div class="ticker-div">
            <CheckboxInput label="Text" />
            <CheckboxInput label="Number" />
            <CheckboxInput label="True/False" />
            <CheckboxInput label="Rating" />
        </div>

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

        .number-input-label {
            font-size: 16px;
        }

        .ticker-div {
            display: flex;
            flex-direction: row;
            justify-content: space-evenly;
            flex-wrap: wrap;
        }
    }
</style>