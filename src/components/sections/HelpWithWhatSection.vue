<script setup lang="ts">
import Carousel from '../ui/Carousel.vue';
import HelpWithWhatItem from '../ui/HelpWithWhatItem.vue';

const helpWithWhatItems = [
    {
        src: '/help-with-one.svg',
        description: 'Наладить гармоничные отношения с близкими людьми',
    },
    {
        src: '/help-with-two.svg',
        description: 'Справиться со стрессом, тревогой и страхом',
    },
    {
        src: '/help-with-three.svg',
        description: 'Принять себя и повысить самооценку',
    },
    {
        src: '/help-with-four.svg',
        description: 'Научиться говорить «нет» и отстаивать личные границы',
    },
    {
        src: '/help-with-five.svg',
        description: 'Пережить перемены: переезд, расставание, потеря работы',
    },
    {
        src: '/help-with-six.svg',
        description: 'Понять, почему на работе проблемы и нет мотивации',
    },
];
</script>

<template>
    <section class="help-with-what">
        <div class="container">
            <h2 id="help-with-what">С чем <span>поможет</span> психолог?</h2>

            <ul>
                <HelpWithWhatItem
                    v-for="helpWithWhatItem in helpWithWhatItems"
                    :src="helpWithWhatItem.src"
                    :description="helpWithWhatItem.description"
                />
            </ul>

            <Carousel class="carousel" :carouselItems="helpWithWhatItems" />

            <div class="button-wrapper">
                <button>Хочу обсудить свою ситуацию</button>
            </div>
        </div>
    </section>
</template>

<style scoped lang="scss">
section.help-with-what {
    display: flex;
    flex-direction: row;
    justify-content: center;
    padding: 70px 0 56px 0;
    width: 100%;

    .container {
        width: 100%;
        max-width: 1440px;
        display: flex;
        flex-direction: column;
        align-items: center;

        h2 {
            font-size: 55px;
            font-weight: 500;

            @media (max-width: 925px) {
                padding: 0 3.3vw 0 3.3vw;
                font-size: 24px;
                align-self: flex-start;
            }

            span {
                color: #42b2fc;
            }
        }

        ul {
            width: 100%;
            max-width: 1140px;
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(330px, 1fr));
            justify-content: space-evenly;
            place-items: center;
            margin-top: 50px;
            list-style-type: none;
            padding: 0;

            @media (max-width: 925px) {
                display: none;
            }
        }
    }

    .carousel {
        display: none;
        margin-top: 80px;
        cursor: default;

        @media (max-width: 925px) {
            display: block;
        }
    }

    .button-wrapper {
        width: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        margin-top: 10px;

        @media (max-width: 925px) {
            margin-top: 35px;
            padding: 0 3.3vw 0 3.3vw;
        }

        button {
            height: 60px;
            width: 390px;
            font-size: 23px;
            font-family: 'Rubik', sans-serif;
            background-color: #45a7f5;
            color: white;
            border: 2px #45a7f5 solid;
            border-radius: 8px;
            cursor: pointer;

            @media (max-width: 925px) {
                height: auto;
                width: 100%;
                padding: 13px;
                font-size: 16px;
                font-weight: 450;
            }

            @media (hover: hover) {
                transition:
                    color 0.2s linear,
                    background-color 0.2s linear;

                &:hover {
                    background: #f0f2f5;
                    color: #45a7f5;
                }
            }

            @media (hover: none) {
                transition:
                    0.07s linear,
                    background-color 0.07s linear;

                &:active {
                    background: #f0f2f5;
                    color: #45a7f5;
                }
            }
        }
    }
}
</style>
