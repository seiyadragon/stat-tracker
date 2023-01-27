
<script>

    export default {
        data() {
            return {
                trackerArray: ref([{
                    formName: "Screen Time",
                    formQuestion: "How many hours did you spend staring at a screen?",
                    formRepeat: 1,
                    formAnswerType: 1,
                }])
            }
        },
        methods: {
            submitData([formData]) {
                this.trackerArray.push(formData)
            }
        }
    }

</script>

<template>

    <main>
        <Head>
            <Title>StatTracker - Home</Title>
            <link rel="favicon" type="image/png" href="/favicon.ico">
            <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Tangerine">
            <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Ubuntu">
        </Head>
        <Header @form-data-received="submitData"/>
        <Panel>
            <section>
                <h1>Stats:</h1>
                <Tracker v-for="tracker in trackerArray" :key="tracker.formName" :form-data="tracker"/>
            </section>
        </Panel>
    </main>

</template>

<style lang="scss">

    body {
        margin: 0%;
        background-image: url("/background.jpg");
        background-size: tile;
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

</style>