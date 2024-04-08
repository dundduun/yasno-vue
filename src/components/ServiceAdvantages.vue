<script setup lang="ts">
import Advantage from './Advantage.vue'

const advantages = [
    {
        src: '/advantage-1.png',
        direction: 'row',
        title: 'Консультации по безопасному видеочату',
        description: 'На нашей платформе видеоконсультации проходят в защищенном личном кабинете'
    },
    {
        src: '/advantage-2.png',
        direction: 'row-reverse',
        title: 'Простое управление расписанием',
        description: 'Назначайте и переносите, мы напомним и не дадим вам забыть'
    },
    {
        src: '/advantage-3.png',
        direction: 'row',
        title: 'Сопровождение на всех этапах',
        description: 'Ответим на вопросы о психологии, поможем, поддержим, объясним, направим'
    },
    {
        src: '/advantage-4.png',
        direction: 'row-reverse',
        title: 'От 2 850 ₽ за сессию',
        description: 'Мы установили минимально возможную цену, чтобы терапия была доступна каждому'
    },
    {
        src: '/advantage-5.png',
        direction: 'row',
        title: 'Оплата картами РФ и иностранных банков',
        description: 'Заботьтесь о своем ментальном здоровье из любой точки мира'
    }
]
</script>


<template>
    <section class="service-advantages">
        <div class="container">
            <h2 class="section-title"><span class="important">
                    Сервис устроен легко и удобно
                </span><br>
                <span class="desktop">Это не наши слова — так считают<br>
                    наши пользователи</span>
                <span class="mobile">
                    Это не наши слова — так считают наши пользователи
                </span>
            </h2>

            <div class="content">
                <div v-for="(item, index) of advantages" class="advantage">
                    <Advantage :src="item.src" :direction="item.direction" :title="item.title"
                        :description="item.description" :key="index" class="advantage"/>
                </div>
            </div>
        </div>
    </section>
</template>


<style>
section.service-advantages {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 90px 3.3vw 90px 3.3vw;
    background-color: #f0f2f5;

    @media(max-width: 925px) {
        padding-top: 0;
    }

    .container {
        width: 100%;
        max-width: 1440px;
        box-sizing: border-box;

        .section-title {
            text-align: center;
            font-weight: 500;
            font-size: 55px;
            margin: 40px 0 0 0;

            @media(max-width: 925px) {
                text-align: left;
                font-size: 24px;
            }

            span.important {
                color: #42b2fc;
            }

            span.desktop {

                @media(max-width: 925px) {
                    display: none;
                }
            }

            span.mobile {
                display: none;

                @media(max-width: 925px) {
                    display: inline;
                }
            }
        }

        .content {
            display: flex;
            flex-direction: column;
            align-items: center;

            .advantage {

                @media(max-width: 925px) {
                    width: 100%;
                }
            }
        }
    }
}
</style>