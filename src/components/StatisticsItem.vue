<script setup>
defineProps([
    'id',
    'title',
    'definitionStart',
    'definitionEnd'
    ])
</script>

<template>
    <span class="element-head">{{ title }}</span>
    <span class="element-definition">{{ definitionStart }}</span>
    <span class="element-definition">{{ definitionEnd }}</span>
</template>

<style scoped lang="scss">

.element-head {
    font-size: 35px;
}

.element-definition {
    font-size: 20px;
    color: #a4afba;
}
</style>