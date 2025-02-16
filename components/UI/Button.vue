<script lang="ts" setup>
    const props = defineProps<{
        label: string,
    }>()
</script>

<template>
    <button class="ui-button">
        {{ label }}
    </button>
</template>

<style scoped lang="scss">
    .ui-button{
        background-color: #3498db;
        color: #fff;
        border: none;
        border-radius: 4px;
        padding: 8px 15px;
        font-size: 0.9rem;
        cursor: pointer;
        transition: background-color 0.3s;

        &:hover {
          background-color: #1d6fa5;
        }
    }
</style>