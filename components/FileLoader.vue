<script lang="ts" setup>
    const props = defineProps<{

    }>()

    const FileLoader = ref<HTMLInputElement | null>(null)
    const file = ref<File | null>(null)



    const dumpFile = () => {
        console.log(FileLoader.value.files)
    }
</script>

<template>
    <input ref="FileLoader" type="file" @change="dumpFile">
</template>

<style lang="scss" scoped>
    input{
        width: 100px;
        height: 100px;
        border: 1px solid black;
    }
</style>