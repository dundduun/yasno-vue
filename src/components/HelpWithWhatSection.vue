<script setup lang="ts">

</script>


<template>
    <div class="section-2">
        <div class="container">
            <h2 id="help-with-what">С чем <span>поможет</span> психолог?</h2>

            <ul>
                <div class="three-items">
                    <li>
                        <img src="@/assets/images/help-with-one.svg" alt="Два человека в объятиях">
                        <p>Наладить гармоничные<br>
                            отношения с близкими людьми
                        </p>
                    </li>

                    <li>
                        <img src="@/assets/images/help-with-two.svg"
                            alt="Умиротворённая девушка, со сложенными в ладонях руками">
                        <p>Справиться со стрессом,<br>
                            тревогой и страхом
                        </p>
                    </li>

                    <li>
                        <img src="@/assets/images/help-with-three.svg" alt="Мужчина с радостью смотрит в зеркало">
                        <p>Принять себя и повысить<br>
                            самооценку
                        </p>
                    </li>
                </div>

                <div class="three-items">
                    <li>
                        <img src="@/assets/images/help-with-four.svg" alt="Девушка за столом держит руку лицевой стороной лодони, 
                            говоря нет без зазрения совести">
                        <p>Научиться говорить «нет»<br>
                            и отстаивать личные границы
                        </p>
                    </li>

                    <li>
                        <img src="@/assets/images/help-with-five.svg" alt="Мужчина держит в руках сердце с маленькими перекрёстными 
                            пластырями">
                        <p>Пережить перемены: переезд,<br>
                            расставание, потеря работы
                        </p>
                    </li>

                    <li>
                        <img src="@/assets/images/help-with-six.svg"
                            alt="Девушка с радостью усердно трудится за компьютером">
                        <p>Понять, почему на работе<br>
                            проблемы и нет мотивации
                        </p>
                    </li>
                </div>
            </ul>

            <button>Хочу обсудить свою ситуацию</button>
        </div>
    </div>
</template>


<style scoped lang="scss">
.section-2 {
    display: flex;
    flex-direction: row;
    justify-content: center;
    padding: 70px 0 90px 0;
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

            span {
                color: #42b2fc;
            }
        }

        ul {
            width: 100%;
            display: flex;
            flex-direction: column;
            list-style-type: none;
            align-items: center;
            margin: 50px 0 0 0;
            padding: 0;

            .three-items {
                width: 100%;
                display: flex;
                flex-flow: row wrap;
                justify-content: space-evenly;
                align-items: baseline;

                li {
                    height: 323px;
                    width: 304px;
                    display: flex;
                    flex-direction: column;
                    align-items: center;

                    img {
                        width: 208px;
                        height: auto;
                    }

                    p {
                        font-size: 20px;
                        margin-top: 25px;
                        line-height: 150%;
                        text-align: center;
                    }
                }
            }
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
            margin-top: 10px;
            cursor: pointer;

            @media(hover: hover) {
                transition: color 0.2s linear,
                    background-color 0.2s linear;

                &:hover {
                    background: #f0f2f5;
                    color: #45a7f5;
                }
            }

            @media(hover: none) {
                transition: 0.07s linear,
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