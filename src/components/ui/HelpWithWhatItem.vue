<script setup lang="ts">
defineProps<{
    src: string;
    description: string;
}>();
</script>

<template>
    <li>
        <img :src="src" />
        <p>{{ description }}</p>
    </li>
</template>

<style scoped lang="scss">
li {
    height: 323px;
    width: 304px;
    display: flex;
    flex-direction: column;
    align-items: center;

    img {
        width: 208px;
        height: 160px;

        @media (max-width: 925px) {
            font-size: 16px;
        }
    }

    p {
        height: 60px;
        width: 305px;
        max-width: 100%;
        margin-top: 25px;
        text-align: center;
        line-height: 150%;
        font-size: 20px;

        @media (max-width: 925px) {
            font-size: 16px;
        }
    }
}
</style>
