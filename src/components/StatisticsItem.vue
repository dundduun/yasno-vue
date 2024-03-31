<script setup lang="ts">
defineProps<{
    title: string;
    definitionStart: string;
    definitionEnd: string
}>()
</script>

<template>
    <span class="element-head">{{ title }}</span>
    <span class="element-definition">{{ definitionStart }}</span>
    <span class="element-definition">{{ definitionEnd }}</span>
</template>

<style scoped lang="scss">

.element-head {
    font-size: 35px;

    @media (max-width: 925px) {
        text-align: start;
        font-size: 22px;
    }
}

.element-definition {
    font-size: 20px;
    color: #a4afba;

    @media (max-width: 925px) {
        text-align: start;
        font-size: 16px;
    }
}
</style>