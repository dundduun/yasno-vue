<script setup lang="ts">
defineProps<{
    source: string;
    direction: string;
    title: string;
    description: string;
}>();
</script>

<template>
    <div class="total-container">
        <div class="wrapper" :class="direction">
            <img :src="source" />

            <div class="text">
                <span class="title">{{ title }}</span>

                <span class="description"> {{ description }}</span>
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss">
.total-container {
    display: flex;
    flex-direction: row;

    .wrapper {
        flex: 1 1 auto;
        display: flex;
        align-items: flex-end;
        justify-content: center;
        gap: 60px;
        margin-top: 100px;
        width: fit-content;

        @media (max-width: 925px) {
            margin-top: 35px;
            align-items: flex-start;
        }

        &.row {
            flex-direction: row;
        }

        &.row-reverse {
            flex-direction: row-reverse;
        }

        @media (max-width: 925px) {
            &.row,
            &.row-reverse {
                flex-direction: column;
            }
        }

        img {
            border-bottom: 1px #ccd3d9 solid;
            width: 530px;
            height: auto;

            @media (max-width: 1090px) {
                align-self: center;
                width: 40vw;
            }

            @media (max-width: 925px) {
                width: 300px;
            }
        }

        .text {
            height: 249px;
            flex: 0 1 400px;
            display: flex;
            flex-direction: column;
            justify-content: center;

            @media (max-width: 925px) {
                height: auto;
                flex: none;
            }

            .title {
                font-weight: 500;
                font-size: 32px;
                line-height: 130%;

                @media (max-width: 925px) {
                    font-size: 21px;
                }
            }

            .description {
                max-width: 400px;
                font-size: 24px;
                color: #7f868f;
                margin-top: 20px;

                @media (max-width: 925px) {
                    font-size: 16px;
                    margin-top: 10px;
                }
            }
        }
    }
}
</style>
