
<script setup>

    let isMenuOpen = ref(false)

    function onTrackClick() {
        isMenuOpen.value = !isMenuOpen.value
    }

</script>

<template>

    <header>
        <img src="favicon.ico" alt="Chart Logo">
        <button @click="onTrackClick()">
            <a href="#">
                <h1>Add</h1>
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
        max-height: 64px;
        border-bottom: 4px solid gold;
        
        padding-left: 384px;
        padding-right: 384px;
        @media (max-width: 400px) {
            padding-left: 24px;
            padding-right: 24px;
        }

        a {
            text-decoration: none;
        }
    
        h1, button a {
            color: gold;
            font-family: 'Tangerine';
        }
    
        button {
            display: flex;
            margin-left: auto;
            background-color: transparent;
            border: none;
            display: table-cell;
            vertical-align: middle;
            transition: transform 0.5s;
            transform: scale(1, 1);
        }
    
        button:hover {
            transform: scale(1.25, 1.25);
        }
    }

</style>