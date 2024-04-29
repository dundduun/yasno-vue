<script setup lang="ts">
defineProps<{
    title: string;
    // definitionStart: string;
    // definitionEnd: string
    definition: string;
    width: string;
}>();
</script>

<template>
    <span class="element-head">{{ title }}</span>
    <span :class="width" class="element-definition">{{ definition }}</span>
</template>

<style scoped lang="scss">
.element-head {
    width: 100%;
    font-size: 35px;

    @media (max-width: 925px) {
        text-align: start;
        font-size: 22px;
    }
}

.width-140px {
    width: 140px;
}

.width-280px {
    width: 280px;
}

.element-definition {
    font-size: 20px;
    color: #a4afba;

    @media (max-width: 925px) {
        text-align: start;
        font-size: 16px;
        width: fit-content;
    }
}
</style>
