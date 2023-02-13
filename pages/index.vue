
<script>

    export default {
        data() {
            return {
                trackerArray: [{
                    formName: "Screen Time",
                    formQuestion: "How many hours did you spend staring at a screen?",
                    formRepeat: 1,
                    formAnswerType: 1,
                }]
            }
        },
        methods: {
            submitData([formData]) {
                this.trackerArray.push(formData)
            },
            removeTracker([name]) {
                let index = 0

                this.trackerArray.forEach((tracker, i) => {
                    if (tracker.formName === name)
                        index = i
                })

                this.trackerArray.splice(index, 1)
            }
        }
    }

</script>

<template>

    <main>
        <Head>
            <Title>StatTracker - Home</Title>
            <link rel="favicon" type="image/png" href="/favicon.ico">
            <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Ubuntu">
        </Head>
        <Header @form-data-received="submitData"/>
        <Panel>
            <section>
                <h1>Stats:</h1>
                <div class="tracker-container">
                    <Tracker v-for="tracker in trackerArray" :key="tracker.formName + tracker.formQuestion" :form-data="tracker" @onTrackerRemove="removeTracker"/>
                </div>
            </section>
        </Panel>
    </main>

</template>

<style lang="scss">

    body {
        margin: 0%;
        background-image: url("/background.jpg");
        background-size: tile;
        font-family: 'Ubuntu';
    }

    ::-webkit-scrollbar {
        width: 3px;
    }

    ::-webkit-scrollbar-track {
      background-color: rgb(98, 74, 46);
    }

    ::-webkit-scrollbar-thumb {
      background-color:  gold;
    }

    ::-webkit-scrollbar-thumb:hover {
      background-color: gold;
    }

    main {
        height: 100vh;
    }

    .tracker-container {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: space-between;
        column-gap: 32px;
        row-gap: 32px;
    }

</style>