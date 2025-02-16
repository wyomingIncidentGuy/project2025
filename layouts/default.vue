<script lang="ts" setup>

</script>

<template>
    <Header />
    <NuxtPage />
    <Footer />
</template>

<style lang="scss">
html,body {
    height: 100%;
    width: 100%;
}

body {
    margin: 0;
    padding: 0;
    height: 100%;
    min-width: 768px;
    font-family: Arial;

    & > #__nuxt {
        display: flex;
        flex-direction: column;
        min-height: 100%;

        & > main {
            flex: 1;
        }
    }
}

.container {
    display: flex;
    max-width: 1200px;
    width: 100%;
    margin: auto;

    @media screen and (max-width: 1220px) {
        max-width: none;
        width: calc(100% - 40px);
        padding: 0 20px;
    }
}

.section-title{
    color: grey;
    font-size: 48px;
    font-weight: bold;
    margin: 20px 0;
}
</style>