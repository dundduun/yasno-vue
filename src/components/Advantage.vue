<script setup lang="ts">
defineProps<{
    advantageNumber: number;
    direction: string;
    title: string;
    description: string
}>()
</script>


<template class>
    <div class="total-container">
        <div class="wrapper" :class="direction">
            <img :src="`/src/assets/images/advantage-${advantageNumber}.png`">

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
        flex: 1 1 1440px;
        margin-top: 100px;
        display: flex;
        align-items: flex-end;
        justify-content: center;
        gap: 60px; 
    
    &.row {
            flex-direction: row;
        }

        &.row-reverse {
            flex-direction: row-reverse;
        }

        img {
            border-bottom: 1px #ccd3d9 solid;
            width: 530px;
            height: 305px;
        }

        .text {
            height: 249px;
            flex: 0 1 521px;
            display: flex;
            flex-direction: column;
            justify-content: center;

            .title {
                font-weight: 500;
                font-size: 32px;
                line-height: 130%;
            }

            .description {
                max-width: 400px;
                font-size: 24px;
                color: #7f868f;
                margin-top: 20px;
            }
        }
    }
}
</style>