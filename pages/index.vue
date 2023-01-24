
<script setup>

</script>

<template>
    <main>
        <Head>
            <Title>StatTracker - Home</Title>
            <link rel="favicon" type="image/png" href="/favicon.ico">
            <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Tangerine">
        </Head>
        <Header />
    </main>
</template>

<style lang="scss">
    body {
        margin: 0%;
        background-image: url("/background.jpg");
        background-size: cover;
    }

    main {
        height: 100vh;
        backdrop-filter: blur(8px) hue-rotate(180deg);
    }
</style>