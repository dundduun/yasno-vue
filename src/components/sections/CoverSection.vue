<script setup lang="ts">
import { ref } from 'vue';
import Slider from '../ui/Slider.vue';

const activeTariff = ref(0);

const tariffs = [
    {
        title: 'Для себя',
        description: '~ 50 мин・от 2 850 ₽',
    },
    {
        title: 'Для двоих',
        description: '~ 1,5 часа・от 4 850 ₽',
    },
];
</script>

<template>
    <div class="cover-section">
        <div class="container">
            <div class="information">
                <h1>
                    <span class="desktop-title">
                        Консультации
                        <br />
                        с психологом онлайн:
                    </span>
                    <span class="mobile-title">
                        Консультации с психологом онлайн:
                    </span>
                    <br />
                    <Slider />
                </h1>

                <div class="clickable-part">
                    <div class="for-who">
                        <button
                            v-for="(tariff, index) of tariffs"
                            :class="{ active: index === activeTariff }"
                            @click="activeTariff = index"
                        >
                            {{ tariff.title }}
                        </button>
                    </div>

                    <span class="price">{{
                        tariffs[activeTariff].description
                    }}</span>

                    <div class="pick-up">
                        <button>Подобрать психолога</button>
                    </div>
                </div>
            </div>

            <div class="image-wrapper">
                <img
                    class="call-session"
                    src="@/assets/images/quality-call-session.png"
                    alt="Психолог на видеозвонке на ноутбуке"
                />
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss">
.cover-section {
    display: flex;
    justify-content: center;
    flex-grow: 1;
    width: 100%;
    background-color: #f0f2f5;

    .container {
        box-sizing: border-box;
        width: 1440px;
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        padding: 40px 0px 80px 3.3vw;

        @media (max-width: 925px) {
            flex-direction: column;
            padding-bottom: 30px;
        }

        .information {
            width: 590px;
            display: flex;
            flex-shrink: 0;
            flex-direction: column;
            align-items: flex-start;
            margin-bottom: 20px;

            @media (max-width: 925px) {
                max-width: none;
                width: 100%;
            }

            h1 {
                flex: 0 1 auto;
                font-size: 53px;
                font-weight: 500;

                @media (max-width: 925px) {
                    align-self: flex-start;
                    font-size: 27px;
                }

                .desktop-title {
                    @media (max-width: 925px) {
                        display: none;
                    }
                }

                .mobile-title {
                    display: none;

                    @media (max-width: 925px) {
                        display: inline;
                    }
                }
            }

            .clickable-part {
                display: flex;
                width: fit-content;
                flex-direction: column;
                align-items: flex-start;
                padding-right: 3.3vw;

                @media (max-width: 925px) {
                    width: 100%;
                }

                .for-who {
                    display: flex;
                    flex-direction: row;
                    margin-top: 70px;
                    width: fit-content;
                    background-color: #e6e8eb;
                    border: 1px #d9dfe4 solid;
                    border-radius: 8px;

                    @media (max-width: 925px) {
                        width: 100%;
                        margin-top: 36px;
                    }

                    button {
                        width: 179px;
                        flex-grow: 1;
                        padding: 15px 20px;
                        border-radius: 8px;
                        border: none;
                        cursor: pointer;
                        font-size: 20px;
                        background-color: #e6e8eb;
                        color: #434343;
                        transition:
                            color 0.5s,
                            background-color 0.5s;
                        font-family: 'Rubik', sans-serif;

                        &.active {
                            background-color: white;
                            color: black;
                        }

                        @media (max-width: 925px) {
                            font-size: 16px;
                            padding: 13px;
                        }
                    }
                }

                .price {
                    align-self: center;
                    color: #6d757c;
                    margin-top: 7px;

                    @media (max-width: 925px) {
                        font-size: 14px;
                    }
                }

                .pick-up {
                    margin-top: 30px;

                    @media (max-width: 925px) {
                        width: 100%;
                    }

                    button {
                        padding: 20px 59px;
                        border: 2px #45a7f5 solid;
                        border-radius: 8px;
                        font-size: 23px;
                        font-family: 'Rubik', sans-serif;
                        background-color: #45a7f5;
                        color: white;
                        cursor: pointer;

                        @media (max-width: 925px) {
                            width: 100%;
                            height: auto;
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
                                color 0.07s linear,
                                background-color 0.07s linear;

                            &:active {
                                background: #f0f2f5;
                                color: #45a7f5;
                            }
                        }
                    }
                }
            }
        }

        .image-wrapper {
            display: flex;
            justify-content: flex-end;
            align-self: center;
            margin-top: 10px;

            @media (max-width: 925px) {
                width: 100%;
            }

            img.call-session {
                height: auto;
                width: 100%;
                max-width: 612px;

                @media (max-width: 925px) {
                    width: 308px;
                }

                @media (max-width: 340px) {
                    width: 100%;
                }
            }
        }
    }
}
</style>
