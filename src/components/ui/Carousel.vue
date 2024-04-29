<script setup lang="ts">
import { Carousel, Pagination, Slide } from 'vue3-carousel';

import 'vue3-carousel/dist/carousel.css';

defineOptions({
    name: 'Autoplay',
    components: {
        Carousel,
        Slide,
        Pagination,
    },
});

defineProps<{
    carouselItems: {
        src: string;
        description: string;
    }[];
}>();
</script>

<template>
    <Carousel class="carousel" :wrap-around="true">
        <Slide
            class="slide"
            v-for="(carouselItem, index) of carouselItems"
            :key="index"
        >
            <div class="carousel__item">
                <img :src="carouselItem.src" />
                <p>{{ carouselItem.description }}</p>
            </div>
        </Slide>

        <template #addons>
            <Pagination class="pagination" />
        </template>
    </Carousel>
</template>

<style scoped lang="scss">
.carousel {
    width: 100%;

    .slide {
        .carousel__item {
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

    .pagination {
        margin-top: 30px;
    }
}
</style>
