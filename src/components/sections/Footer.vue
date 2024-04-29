<script setup lang="ts">
import FooterLinksItem from './FooterLinksItem.vue';
import { DateTime } from 'luxon';

const currentYear = DateTime.now().toObject().year;

const footerLinksData = [
    {
        title: 'О, ясно',
        links: [
            {
                name: 'Вопросы-ответы',
                linkHref: 'https://yasno.live/faq',
            },
            {
                name: 'Контакты',
                linkHref: 'https://yasno.live/contacts',
            },
            {
                name: 'Вакансии',
                linkHref: 'https://work.yasno.live/',
            },
            {
                name: 'Ясно для бизнеса',
                linkHref: 'https://business.yasno.live/',
            },
        ],
    },
    {
        title: 'Полезное',
        links: [
            {
                name: 'Каталог психологов',
                linkHref: 'https://yasno.live/therapists',
            },
            {
                name: 'Бесплатная помощь',
                linkHref: 'https://yasno.live/free-psychological-help',
            },
            {
                name: 'Психологические тесты',
                linkHref: 'https://yasno.live/tests',
            },
            {
                name: 'Статьи о психологии',
                linkHref: 'https://yasno.live/blog',
            },
        ],
    },
    {
        title: 'Ещё',
        links: [
            {
                name: 'Подарочные сертификаты',
                linkHref: 'https://yasno.live/gifts',
            },
            {
                name: 'Правила акций',
                linkHref: 'https://yasno.live/promo',
            },
            {
                name: 'Пользовательское соглашение',
                linkHref: 'https://yasno.live/terms',
            },
            {
                name: 'Обработка персональных данных',
                linkHref: 'https://yasno.live/personaldata',
            },
            {
                name: 'Согласие на обработку',
                linkHref: 'https://yasno.live/consent',
            },
        ],
    },
];
</script>

<template>
    <footer>
        <div class="container">
            <div class="phone-download">
                <a
                    href="https://apps.apple.com/ru/app/%D1%8F%D1%81%D0%BD%D0%BE-%D0%BF%D1%81%D0%B8%D1%85%D0%BE%D0%BB%D0%BE%D0%B3%D0%B8-%D0%BE%D0%BD%D0%BB%D0%B0%D0%B9%D0%BD/id1584370233?mt=8"
                >
                    Скачать приложение
                </a>
            </div>

            <div class="desktop">
                <div class="download">
                    <a
                        class="by-qr"
                        href="https://apps.apple.com/ru/app/%D1%8F%D1%81%D0%BD%D0%BE-%D0%BF%D1%81%D0%B8%D1%85%D0%BE%D0%BB%D0%BE%D0%B3%D0%B8-%D0%BE%D0%BD%D0%BB%D0%B0%D0%B9%D0%BD/id1584370233?mt=8"
                    >
                        <img
                            class="line-under-qr"
                            src="@/assets/images/line-under-qr.svg"
                        />
                        <div class="absolute-content">
                            <img
                                src="@/assets/images/qr-download.svg"
                                alt="Qr-code for download"
                                class="qr"
                            />
                            <span>Скачать приложение</span>
                        </div>
                    </a>
                    <div class="app-stores">
                        <a
                            href="https://apps.apple.com/ru/app/%D1%8F%D1%81%D0%BD%D0%BE-%D0%BF%D1%81%D0%B8%D1%85%D0%BE%D0%BB%D0%BE%D0%B3%D0%B8-%D0%BE%D0%BD%D0%BB%D0%B0%D0%B9%D0%BD/id1584370233?mt=8"
                        >
                            <img
                                src="@/assets/images/app-store-download.svg"
                                class="application-store"
                                alt="Download in App Store"
                            />
                        </a>
                        <a
                            href="https://app.appsflyer.com/live.yasno.app?pid=12&utm_source=footer"
                        >
                            <img
                                src="@/assets/images/google-play-download.svg"
                                class="application-store"
                                alt="Download in Google Play"
                            />
                        </a>
                    </div>
                </div>

                <div class="footer-links-items">
                    <FooterLinksItem
                        v-for="linksSection in footerLinksData"
                        :title="linksSection.title"
                        :links="linksSection.links"
                    />
                </div>

                <div class="social-media">
                    <div class="main-socials">
                        <span>© 2017–{{ currentYear }} Ясно</span>

                        <div class="four-media-icons">
                            <a href="https://vk.com/yasnotherapy">
                                <img
                                    src="@/assets/images/vk.svg"
                                    alt="Мы Вконтакте"
                                />
                            </a>
                            <a
                                href="https://dzen.ru/yasnolive?utm_referrer=yasno.live"
                            >
                                <img
                                    src="@/assets/images/ya-dzen.svg"
                                    alt="Мы в Яндекс Дзен"
                                />
                            </a>
                            <a href="https://t.me/yasno_live">
                                <img
                                    src="@/assets/images/telegram.svg"
                                    alt="Мы в Телеграме"
                                />
                            </a>
                            <a
                                href="https://www.youtube.com/c/%D0%AF%D1%81%D0%BD%D0%BE%D0%BB%D0%B0%D0%B9%D0%B2"
                            >
                                <img
                                    src="@/assets/images/youtube.svg"
                                    alt="Мы в Youtube"
                                />
                            </a>
                        </div>
                    </div>

                    <a
                        class="sk-resident"
                        href="https://navigator.sk.ru/orn/1124519"
                    >
                        <img
                            class="skolkovo-icon"
                            src="@/assets/images/skolkovo.svg"
                            alt="Мы на sk.ru"
                        />
                    </a>
                </div>
            </div>
        </div>
    </footer>
</template>

<style scoped lang="scss">
footer {
    display: flex;
    flex-direction: row;
    justify-content: center;
    width: 100%;
    padding: 40px 20px 40px 20px;
    background-color: white;

    .container {
        display: flex;
        flex-direction: column;
        width: 100%;
        max-width: 1100px;

        .phone-download {
            display: none;
            justify-content: center;

            @media (max-width: 1022px) {
                display: flex;
            }

            a {
                flex-grow: 1;
                padding: 15px;
                transition: 0.22s;
                border: none;
                border-radius: 10px;
                cursor: pointer;
                color: #0496f6;
                background-color: #ecf6fe;
                font-size: 18px;
                font-weight: 500;
                text-align: center;
                text-decoration: none;

                &:hover {
                    background-color: #e1f0fe;
                }
            }
        }

        .desktop {
            width: 100%;
            display: flex;
            flex-direction: row;
            justify-content: center;
            flex-wrap: wrap;
            margin-top: 10px;

            @media (max-width: 1022px) {
                flex-direction: column;
            }

            .download {
                padding: 10px;

                @media (max-width: 1022px) {
                    display: none;
                }

                .by-qr {
                    display: flex;
                    text-decoration: none;

                    img.line-under-qr {
                        width: 160px;
                        height: 50px;
                        background-color: #f3f5f6;
                        border-radius: 10px;
                    }

                    .absolute-content {
                        position: absolute;
                        width: 160px;
                        display: flex;
                        flex-direction: row;
                        align-items: center;
                        padding: 4px 4px 4px 10px;
                        border-radius: 10px;

                        img.qr {
                            height: 40px;
                            width: 40px;
                        }

                        span {
                            margin-left: 14px;
                            font-size: 11px;
                            color: #345066;
                        }
                    }
                }

                .app-stores {
                    margin-top: 5px;
                    width: 160px;
                    display: flex;
                    flex-direction: row;
                    justify-content: space-between;

                    .application-store {
                        width: 78px;
                        height: 24px;
                    }
                }
            }

            .footer-links-items {
                display: flex;
                flex-flow: row wrap;
                justify-content: space-evenly;
                flex-grow: 1;
                margin-top: 10px;

                @media (max-width: 1022px) {
                    justify-content: flex-start;
                    gap: 5vw;
                }
            }

            .social-media {
                height: 130px;
                display: flex;
                flex-direction: column;
                justify-content: space-between;
                align-items: flex-end;
                padding: 10px;

                @media (max-width: 1022px) {
                    flex-flow: row wrap;
                    align-items: center;
                    flex: 1 1 auto;
                }

                .main-socials {
                    display: flex;
                    flex-direction: column;
                    align-items: flex-end;
                    gap: 15px;

                    @media (max-width: 1022px) {
                        flex-direction: column-reverse;
                        align-items: flex-start;
                    }

                    span {
                        font-size: 14px;
                        color: #345066;
                    }

                    .four-media-icons {
                        display: flex;
                        flex-direction: row;
                        gap: 8px;

                        img {
                            height: 32px;
                            width: 32px;
                        }
                    }
                }

                a.sk-resident {
                    img.skolkovo-icon {
                        height: 22px;
                        width: 68px;
                    }
                }
            }
        }
    }
}
</style>
