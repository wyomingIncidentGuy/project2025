<script lang="ts" setup>
const props = withDefaults(
    defineProps<{
        padding?: string
    }>(),
    {
        padding: "40px",
    },
)
</script>

<template>
    <div
        :style="{ '--padding': padding }"
        class="ui-card"
    >
        <slot />
    </div>
</template>

<style lang="scss" scoped>
.ui-card {
    $padding: var(--padding);
    box-sizing: border-box;
    background-color: white;
    padding: $padding;
    border-radius: 15px;
}
</style>
