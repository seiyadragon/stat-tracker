
<script lang="ts">

    export enum AnswerType {

    }

    export default {
    props: ["formData"],
    methods: {
        getAnswerType(answerType) {
            
        }
    }
}

</script>


<template>

    <div>
        <div class="title">
            <p>{{ formData.formName }}</p>
            <button>Remove</button>
        </div>
        <div class="tracker-body">
            <div class="tracker-body-left">
                <p>Repeats every {{ formData.formRepeat }} {{ formData.formRepeat === 1 ? 'day' : 'days'}}</p>
                <p>{{ formData.formQuestion }}</p>
            </div>
            <div class="tracker-body-right">
                <AnswerInput type="Test"/>
            </div>
        </div>
    </div>

</template>

<style lang="scss" scoped>

    div {
        padding-top: 8px;
        padding-bottom: 8px;

        margin-bottom: 16px;

        border: 2px solid gold;
        border-radius: 24px;

        display: flex;
        flex-direction: column;

        padding: 8px;

        .title {
            display: flex;
            flex-direction: row;
            border: none;
            border-bottom: solid 2px gold;
            border-radius: 0;

            button {
                font-family: 'Tangerine';
                background-color: transparent;
                border: none;
                font-size: 32px;
                color: white;
                justify-self: end;
                margin-left: auto;
                transform: scale(1, 1);
                transition: transform 0.5s;
            }

            button:hover {
                transform: scale(1.25, 1.25);
                transition: transform 0.5s;
            }

            p {
                justify-self: left;
                margin-right: auto;
                font-size: 24px;
                font-family: 'Ubuntu';
            }
        }

        .tracker-body {
            border: none;
            display: flex;
            flex-direction: row;

            .tracker-body-left {
                width: 50%;
                border: none;
                border-radius: 0px;
            }

            .tracker-body-right {
                width: 50%;
                border: none;
                border-radius: 0px;
                text-align: right;
            }
        }

    }

</style>