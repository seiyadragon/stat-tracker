
<script>
    import CheckboxInput from './CheckboxInput.vue';
    import { AnswerType } from './Tracker.vue';

    export default {
    props: {
        type: AnswerType
    },
    data() {
        return {
            canTickSelectors: [true, true],
        }
    },
    methods: {
        onCheckboxClick([valueID, isTicked]) {
            let updatedList = []
    
            if (isTicked) {
                this.canTickSelectors.map((selector) => {
                    selector = false
                    updatedList.push(selector)
                })
    
                updatedList[valueID] = true
            } else {
                this.canTickSelectors.map((selector) => {
                    selector = true
                    updatedList.push(selector)
                })
            }
    
            this.canTickSelectors = updatedList
        },
    },
    components: { CheckboxInput }
}

</script>

<template>

    <div class="answer">
        <div>
            <input type="text" v-if="type === 'Text'">
        </div>
        <div>
            <NumberInput v-if="type === 'Number'">
                <label>Number</label>
            </NumberInput>
        </div>
        <div>
            <CheckboxInput v-if="type === 'TrueFalse'" class="checkbox" :can-tick="canTickSelectors[0]" label="True" :value-i-d="0" @checkbox-clicked="onCheckboxClick" />
            <CheckboxInput v-if="type === 'TrueFalse'" class="checkbox" :can-tick="canTickSelectors[1]" label="False" :value-i-d="1" @checkbox-clicked="onCheckboxClick" />
        </div>
        <div>
            <NumberInput v-if="type === 'Rating'">
                <label>Rating</label>
            </NumberInput>
        </div>
        <div>
            <NumberInput v-if="type === 'Streak'">
                <label>Streak</label>
            </NumberInput>
        </div>
    </div>

</template>

<style lang="scss" scoped>

    .answer {
        border: none;
        border-radius: 0px;
        height: 100%;
        display: flex;
        flex-direction: column;

        p {
            justify-self: right;
            margin-left: auto;
            margin-bottom: auto;
        }

        .checkbox {
            text-align: center;
        }
    }

</style>

<style lang="scss">
    .answer {
        input, button[type=button] {
            border: none;
            background-color: transparent;
            font-size: 16px;
            border-bottom: solid 2px white;
            color: white;
            max-width: 100%;
        }

        input:focus {
            outline: none;
        }
    }
</style>