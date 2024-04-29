<script setup lang="ts">
import { onMounted } from 'vue';
import { gsap } from 'gsap';

let mm = gsap.matchMedia();

onMounted(() => {
    let tl = gsap.timeline({ repeat: 5 });

    mm.add('(min-width: 926px)', () => {
        tl.to(
            '.slider-item',
            { duration: 0.8, y: -126, ease: 'power4' },
            '>2.5',
        );
        tl.to(
            '.slider-item',
            { duration: 0.8, y: -252, ease: 'power4' },
            '>2.5',
        );
        tl.to(
            '.slider-item',
            { duration: 0.8, y: -378, ease: 'power4' },
            '>2.5',
        );
        tl.to(
            '.slider-item',
            { duration: 0.8, y: -504, ease: 'power4' },
            '>2.5',
        );
        tl.to(
            '.slider-item',
            { duration: 0.8, y: -630, ease: 'power4' },
            '>2.5',
        );
        tl.to('.slider-item', { duration: 0.8, y: 0, ease: 'power4' }, '>2.5');
    });

    mm.add('(max-width: 925px)', () => {
        tl.to(
            '.slider-item',
            { duration: 0.8, y: -66, ease: 'power4' },
            '>2.5',
        );
        tl.to(
            '.slider-item',
            { duration: 0.8, y: -132, ease: 'power4' },
            '>2.5',
        );
        tl.to(
            '.slider-item',
            { duration: 0.8, y: -198, ease: 'power4' },
            '>2.5',
        );
        tl.to(
            '.slider-item',
            { duration: 0.8, y: -264, ease: 'power4' },
            '>2.5',
        );
        tl.to(
            '.slider-item',
            { duration: 0.8, y: -330, ease: 'power4' },
            '>2.5',
        );
        tl.to('.slider-item', { duration: 0.8, y: 0, ease: 'power4' }, '>2.5');
    });
});
</script>

<template>
    <ul class="slider-list">
        <li class="slider-item">повысить качество жизни</li>
        <li class="slider-item desktop">справиться<br />со стрессом</li>
        <li class="slider-item mobile">справиться со стрессом</li>
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

    @media (max-width: 925px) {
        height: 66px;
    }

    li {
        height: 126px;
        font-size: 53px;
        color: #42b2fc;
        width: 100%;

        &.mobile {
            display: none;
        }

        @media (max-width: 925px) {
            height: 66px;
            font-size: 27px;

            &.desktop {
                display: none;
            }

            &.mobile {
                display: block;
            }
        }
    }
}
</style>
