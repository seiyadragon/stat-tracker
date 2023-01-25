
<script setup>

    let isMenuOpen = ref(false)

    function onTrackClick() {
        isMenuOpen.value = !isMenuOpen.value
    }

</script>

<template>

    <header>
        <NuxtLink to="/">
            <h1>Track your stats!</h1>
        </NuxtLink>
        <button @click="onTrackClick()">
            <a href="#">
                <h1>Track</h1>
            </a>
        </button>
    </header>

    <Popup v-if="isMenuOpen === true" @onBackClick="onTrackClick">
        <TrackForm />
    </Popup>

</template>

<style lang="scss" scoped>

    header {
        background-color: rgb(98, 74, 46);
        backdrop-filter: blur(25px);
        padding: 0.25em;
        display: sticky;
        display: flex;
        padding-left: 24px;
        padding-right: 24px;

        border-bottom: 4px solid gold;
    }
    
    a {
        text-decoration: none;
    }

    h1, button a {
        color: gold;
        font-family: 'Tangerine';
        font-size: 42px;
    }

    button {
        display: flex;
        margin-left: auto;
        background-color: transparent;
        border: none;
        display: table-cell;
        vertical-align: middle;
        transition: transform 0.25s;

        :hover {
            transform: scale(1.25, 1.25);
        }
    }

</style>