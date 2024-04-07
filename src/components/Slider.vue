<script setup lang="ts">
import { onMounted } from 'vue'
import { gsap } from 'gsap'

onMounted(() => {
    let tl = gsap.timeline({ repeat: 5 });
    tl.to('.slider-item', {duration: 0.5, y: -126, ease: 'power4' }, '>2.5');
    tl.to('.slider-item', {duration: 0.5, y: -252, ease: 'power4' }, '>2.5');
    tl.to('.slider-item', {duration: 0.5, y: -378, ease: 'power4' }, '>2.5');
    tl.to('.slider-item', {duration: 0.5, y: -504 , ease: 'power4' }, '>2.5');
    tl.to('.slider-item', {duration: 0.5, y: -630 , ease: 'power4' }, '>2.5');
    tl.to('.slider-item', {duration: 0.5, y: 0, ease: 'power4'}, '>2.5')
})
</script>


<template>
    <ul class="slider-list">
        <li class="slider-item">повысить качество жизни</li>
        <li class="slider-item">справиться<br>
            со стрессом</li>
        <li class="slider-item">наладить отношения с близкими</li>
        <li class="slider-item">найти своё призвание</li>
        <li class="slider-item">принять себя</li>
        <li class="slider-item">обрести спокойствие</li>
    </ul>
</template>

<style scoped lang="scss">
ul {
    height: 126px;
    overflow: hidden;
    list-style-type: none;
    margin: 0;
    padding: 0;

    li {
        height: 126px;
        font-size: 53px;
        color: #42b2fc;
        width: 100%;

        // transform: translateY(-380px);
    }
}
</style>
