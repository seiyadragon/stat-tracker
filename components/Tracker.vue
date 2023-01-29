
<script lang="ts">

    export enum AnswerType {
        Text = 0,
        Number = 1,
        TrueFalse = 2,
        Rating = 3,
        Streak = 4,
    }

    export default {
    props: ["formData"],
    methods: {
        getAnswerType(answerType: number) {
            return AnswerType[answerType]
        }
    }
}

</script>


<template>

    <section>
        <div class="title">
            <div>
                <h1>{{ formData.formName }}</h1>
                <h5>Repeats every {{ formData.formRepeat }} {{ formData.formRepeat === 1 ? 'day' : 'days'}}</h5>
            </div>
            <button @click="$emit('onTrackerRemove', [formData.formName])">Remove</button>
        </div>
        <div class="tracker-body">
            <p>{{ formData.formQuestion }}</p>
            <AnswerInput :type="getAnswerType(formData.formAnswerType)"/>
        </div>
        <div class="graph-area">
            <h1>Data</h1>
            <Graph />
        </div>
    </section>

</template>

<style lang="scss" scoped>

    section {
        div {
            padding-top: 4px;
            padding-bottom: 4px;
        }

        padding-top: 8px;
        padding-bottom: 8px;

        margin-bottom: 4px;

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

            h1 {
                margin-bottom: 0;
                padding-bottom: 0;
                padding-top: 0;
                margin-top: 0;
            }

            h5 {
                margin-top: 0;
                color: rgb(155, 155, 155);
                padding-bottom: 0;
                margin-bottom: 0;
            }

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
        }

        .graph-area {
            border: none;
            padding-left: 2px;
            padding-right: 2px;
            border-radius: 0px;
        }
    }

</style>