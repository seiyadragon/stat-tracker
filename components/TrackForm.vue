

<script setup>

    let formData = ref({
        formName: "",
        formQuestion: "",
        formRepeat: 0,
        formAnswerType: -1,
    })

    let canTickSelectors = ref([true, true, true, true, true])

    function onCheckboxClick([valueID, isTicked]) {
        let updatedList = []

        if (isTicked) {
            canTickSelectors.value.map((selector) => {
                selector = false
                updatedList.push(selector)
            })

            updatedList[valueID] = true
            formData.value.formAnswerType = valueID
        } else {
            canTickSelectors.value.map((selector) => {
                selector = true
                updatedList.push(selector)
            })

            formData.value.formAnswerType = -1
        }

        canTickSelectors.value = updatedList
    }

    function numberInputValueChange([value]) {
        formData.value.formRepeat = value
    }

</script>

<template>

    <form>
        <label>Name:</label>
        <input type="text" v-model="formData.formName">

        <label>Question:</label>
        <input type="text" v-model="formData.formQuestion">

        <label>Repeat:</label>
        <NumberInput @value-change="numberInputValueChange">
            <label class="number-input-label">Days</label>
        </NumberInput>

        <label>Answer Type:</label>
        <div class="ticker-div">
            <CheckboxInput :can-tick="canTickSelectors[0]" label="Text" :value-i-d="0" @checkbox-clicked="onCheckboxClick" />
            <CheckboxInput :can-tick="canTickSelectors[1]" label="Number" :value-i-d="1" @checkbox-clicked="onCheckboxClick" />
            <CheckboxInput :can-tick="canTickSelectors[2]" label="True/False" :value-i-d="2" @checkbox-clicked="onCheckboxClick" />
            <CheckboxInput :can-tick="canTickSelectors[3]" label="Rating" :value-i-d="3" @checkbox-clicked="onCheckboxClick" />
            <CheckboxInput :can-tick="canTickSelectors[4]" label="Streak" :value-i-d="4" @checkbox-clicked="onCheckboxClick" />
        </div>

        <div class="submit">
            <button type="button" @click="$emit('data-submitted', [formData])">Add</button>
        </div>
    </form>

</template>

<style lang="scss">
    form {
        display: flex;
        flex-direction: column;
        padding-top: 2em;
        padding-bottom: 2em;
        height: 56vh;
        
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
            border-bottom: solid 2px white;
        }

        .submit {
            display: flex;

            margin-top: auto;
            margin-bottom: auto;

            padding: 0;

            button {
                margin-top: 0;
                margin-bottom: 0;
                margin-left: auto;
                margin-right: auto;

                font-size: 32px;
                font-family: 'Tangerine';

                border: none;

                transition: transform 0.5s;
                transform: scale(1, 1);
            }
    
            button:hover {
                transform: scale(1.25, 1.25);
            }
        }
    }
</style>