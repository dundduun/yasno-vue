<script setup lang="ts">
import { Carousel, Pagination, Slide } from 'vue3-carousel'

import 'vue3-carousel/dist/carousel.css'

defineOptions({
    name: 'Autoplay',
    components: {
        Carousel,
        Slide,
        Pagination,
    }
})

defineProps<{
    helpWithWhatItems: {
        src: string,
        description: string,
    }[],
}>()


</script>

<template>
    <Carousel class="carousel" :wrap-around="true">
        <Slide class="slide" v-for="(helpWithWhatItem, index) of helpWithWhatItems" 
        :key="index">
            <div class="carousel__item">
                <img :src="helpWithWhatItem.src">
                <p>{{helpWithWhatItem.description }}</p>
            </div>
        </Slide>

        <template #addons>
            <Pagination />
        </template>
    </Carousel>
</template>

<style scoped lang="scss">
.carousel {
    width: 100%;

    .slide {

        .carousel__item {
            // width: 304px;
            display: flex;
            flex-direction: column;
            align-items: center;

            img {
                width: 208px;
                height: 160px;
            }

            p {
                max-width: 100%;
                margin-top: 25px;
                padding: 0 10px 0 10px;
                line-height: 150%;
                text-align: center;
                font-size: 16px;
            }

        }
    }
}
</style>