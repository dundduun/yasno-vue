<script setup lang="ts">
import { ref } from 'vue'
import StatisticsItem from './components/StatisticsItem.vue'
import Advantage from './components/Advantage.vue'
import FooterLinksItem from './components/FooterLinksItem.vue'

const activeTariff = ref(0);

const tariffs = [
  {
    title: 'Для себя',
    description: '~ 50 мин・от 2 850 ₽'
  },
  {
    title: 'Для двоих',
    description: '~ 1,5 часа・от 4 850 ₽'
  }
]

const statisticsItems = [
  {
    title: '270 000+',
    definitionStart: 'человек нашли своего',
    definitionEnd: 'психолога онлайн'
  },
  {
    title: '4 100',
    definitionStart: 'проверенных',
    definitionEnd: 'специалистов'
  },
  {
    title: '7 лет',
    definitionStart: 'средний опыт',
    definitionEnd: 'практики'
  },
  {
    title: '81%',
    definitionStart: 'клиентов чувствуют',
    definitionEnd: 'результат после 5-й сессии'
  }
]

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

const footerLinksData = [
  {
    title: 'О, ясно',
    links: [
      {
        name: 'Вопросы-ответы',
        linkHref: 'https://yasno.live/faq'
      },
      {
        name: 'Контакты',
        linkHref: 'https://yasno.live/contacts'
      },
      {
        name: 'Вакансии',
        linkHref: 'https://work.yasno.live/'
      },
      {
        name: 'Ясно для бизнеса',
        linkHref: 'https://business.yasno.live/'
      }
    ]
  },
  {
    title: 'Полезное',
    links: [
      {
        name: 'Каталог психологов',
        linkHref: 'https://yasno.live/therapists'
      },
      {
        name: 'Бесплатная помощь',
        linkHref: 'https://yasno.live/free-psychological-help'
      },
      {
        name: 'Психологические тесты',
        linkHref: 'https://yasno.live/tests'
      },
      {
        name: 'Статьи о психологии',
        linkHref: 'https://yasno.live/blog'
      }
    ]
  },
  {
    title: 'Ещё',
    links: [
      {
        name: 'Подарочные сертификаты',
        linkHref: 'https://yasno.live/gifts'
      },
      {
        name: 'Правила акций',
        linkHref: 'https://yasno.live/promo'
      },
      {
        name: 'Пользовательское соглашение',
        linkHref: 'https://yasno.live/terms'
      },
      {
        name: 'Обработка персональных данных',
        linkHref: 'https://yasno.live/personaldata'
      },
      {
        name: 'Согласие на обработку  ',
        linkHref: 'https://yasno.live/consent'
      }
    ]
  }
]

</script>

<template>
  <div class="header-container">
    <div class="header">
      <a href="#" class="title">ЯСНО</a>
      <a href="#help-with-what" class="help-with-what-anchor">С чем поможет психолог?</a>
    </div>
  </div>

  <div class="section-1-container">
    <div class="content">
      <div class="left-side">
        <h1>Консультации с психологом онлайн:<br>
          <span>обрести спокойствие</span>
        </h1>
        <div class="clickable-part">
          <div class="for-who">
            <button v-for="(tariff, index) of tariffs" :class="{ active: index === activeTariff }"
              @click="activeTariff = index">{{ tariff.title }}</button>
          </div>

          <span id="price">{{ tariffs[activeTariff].description }}</span>
          <div class="pick-up">
            <button>Подобрать психолога</button>
          </div>
        </div>
      </div>

      <div class="images">
        <img class="man-on-laptop-call" src="@/assets/images/quality-call-session.png"
          alt="Психолог на видеозвонке на ноутбуке">
      </div>

    </div>
  </div>

  <div class="statistics">
    <ul>
      <li v-for="(item, index) in statisticsItems">
        <StatisticsItem :key="index" :title="item.title" :definitionStart="item.definitionStart"
          :definitionEnd="item.definitionEnd" />
      </li>
    </ul>
  </div>

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
            <img src="@/assets/images/help-with-two.svg" alt="Умиротворённая девушка, со сложенными в ладонях руками">
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
            <img src="@/assets/images/help-with-four.svg"
              alt="Девушка за столом держит руку лицевой стороной лодони, говоря нет без зазрения совести">
            <p>Научиться говорить «нет»<br>
              и отстаивать личные границы
            </p>
          </li>

          <li>
            <img src="@/assets/images/help-with-five.svg"
              alt="Мужчина держит в руках сердце с маленькими перекрёстными пластырями">
            <p>Пережить перемены: переезд,<br>
              расставание, потеря работы
            </p>
          </li>

          <li>
            <img src="@/assets/images/help-with-six.svg" alt="Девушка с радостью усердно трудится за компьютером">
            <p>Понять, почему на работе<br>
              проблемы и нет мотивации
            </p>
          </li>
        </div>
      </ul>

      <button>Хочу обсудить свою ситуацию</button>
    </div>
  </div>

  <section class="service-advantages">
    <div class="container">
      <h2 class="section-title"><span>Сервис устроен легко и удобно</span><br>
        Это не наши слова — так считают<br>
        наши пользователи
      </h2>

      <div class="content">
        <div v-for="(item, index) of advantages" class="advantage">
          <Advantage :src="item.src" :direction="item.direction" :title="item.title" :description="item.description"
            :key="index" />
        </div>
      </div>
    </div>
  </section>

  <footer>
    <div class="container">
      <div class="download">
        <a class="by-qr"
          href="https://apps.apple.com/ru/app/%D1%8F%D1%81%D0%BD%D0%BE-%D0%BF%D1%81%D0%B8%D1%85%D0%BE%D0%BB%D0%BE%D0%B3%D0%B8-%D0%BE%D0%BD%D0%BB%D0%B0%D0%B9%D0%BD/id1584370233?mt=8">
          <img class="line-under-qr" src="@/assets/images/line-under-qr.svg">
          <div class="absolute-content">
            <img src="@/assets/images/qr-download.svg" alt="Qr-code for download" class="qr">
            <span>Скачать приложение</span>
          </div>
        </a>
        <div class="app-stores">
          <a
            href="https://apps.apple.com/ru/app/%D1%8F%D1%81%D0%BD%D0%BE-%D0%BF%D1%81%D0%B8%D1%85%D0%BE%D0%BB%D0%BE%D0%B3%D0%B8-%D0%BE%D0%BD%D0%BB%D0%B0%D0%B9%D0%BD/id1584370233?mt=8">
            <img src="@/assets/images/app-store-download.svg" class="application-store" alt="Download in App Store">
          </a>
          <a href="https://app.appsflyer.com/live.yasno.app?pid=12&utm_source=footer">
            <img src="@/assets/images/google-play-download.svg" class="application-store" alt="Download in Google Play">
          </a>
        </div>
      </div>

      <FooterLinksItem v-for="linksSection in footerLinksData" :title="linksSection.title"
        :links="linksSection.links" />

      <div class="social-media">
        <span>© 2017–2024 Ясно</span>

        <div class="four-media-icons">
          <a href="https://vk.com/yasnotherapy">
            <img src="@/assets/images/vk.svg" alt="Мы Вконтакте">
          </a>
          <a href="https://dzen.ru/yasnolive?utm_referrer=yasno.live">
            <img src="@/assets/images/ya-dzen.svg" alt="Мы в Яндекс Дзен">
          </a>
          <a href="https://t.me/yasno_live">
            <img src="@/assets/images/telegram.svg" alt="Мы в Телеграме">
          </a>
          <a href="https://www.youtube.com/c/%D0%AF%D1%81%D0%BD%D0%BE%D0%BB%D0%B0%D0%B9%D0%B2">
            <img src="@/assets/images/youtube.svg" alt="Мы в Youtube">
          </a>
        </div>
        <a href="https://navigator.sk.ru/orn/1124519">
          <img class="skolkovo-icon" src="@/assets/images/skolkovo.svg" alt="Мы ">
        </a>
      </div>
    </div>

  </footer>

</template>

<style lang="scss">
* {
  box-sizing: border-box;
  margin: 0;
}

section,
footer,
div {
  overflow: hidden;
  overflow-wrap: normal;
}



.header-container {
  display: flex;
  justify-content: center;
  width: 100%;

  .header {
    box-sizing: border-box;
    width: 1440px;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    flex-grow: 0;
    padding: 15px 3.3vw;
    background-color: white;

    .title {
      font-size: 35px;
      color: #42b2fc;
      font-weight: bold;
      text-decoration: none;
    }

    .help-with-what-anchor {
      padding: 10px 0px 10px 10px;
      color: black;
      transition: 0.3s;
      text-decoration: none;
    }

    .help-with-what-anchor:hover {
      color: #42b2fc;
    }
  }
}

.section-1-container {
  display: flex;
  justify-content: center;
  flex-grow: 1;
  width: 100%;
  background-color: #f0f2f5;

  .content {
    box-sizing: border-box;
    width: 1440px;
    display: flex;
    flex-flow: wrap row;
    justify-content: center;
    padding: 40px 0px 80px 3.3vw;

    .left-side {
      max-width: 540px;
      display: flex;
      flex: 1 1 auto;
      margin-bottom: 20px;
      flex-direction: column;
      align-items: center;

      h1 {
        max-width: 540px;
        flex: 0 1 auto;
        font-size: 53px;
        font-weight: 500;

        span {
          color: #42b2fc;
        }
      }

      .clickable-part {
        display: flex;
        width: fit-content;
        flex-direction: column;
        align-items: flex-start;

        .for-who {
          margin-top: 70px;
          width: fit-content;
          background-color: #e6e8eb;
          border: 1px #d9dfe4 solid;
          border-radius: 8px;

          button {
            transition: 0.5s;
            border: none;
            width: 179px;
            border-radius: 8px;
            font-family: "Rubik", sans-serif;
            font-size: 20px;
            padding: 15px 20px;
            background-color: #e6e8eb;
            color: #434343;
            cursor: pointer;

            &.active {
              background-color: white;
              color: black;
            }
          }
        }

        #price {
          color: #6d757c;
          margin-top: 7px;
          align-self: center;
        }

        .pick-up {
          margin-top: 30px;

          button {
            height: 70px;
            width: 358px;
            font-size: 23px;
            font-family: 'Rubik', sans-serif;
            background-color: #45a7f5;
            color: white;
            border: 2px #45a7f5 solid;
            border-radius: 8px;
            cursor: pointer;
          }

          @media (hover: hover) {
            button {
              transition: 0.2s linear;
            }

            button:hover {
              background: #f0f2f5;
              color: #45a7f5;
            }
          }

          @media (hover: none) {
            button {
              transition: 0.07s linear;
            }

            button:active {
              background: #f0f2f5;
              color: #45a7f5;
            }
          }
        }
      }
    }

    .images {
      display: flex;
      justify-content: flex-end;
      flex: 1 1 auto;
      align-self: center;
      margin-top: 10px;

      .man-on-laptop-call {
        height: auto;
        width: 90%;
        max-width: 650px;
      }
    }
  }
}

.statistics {
  width: 100%;
  display: flex;
  flex-direction: row;
  justify-content: center;
  padding: 20px 0 20px 0;
  border-bottom: 1px #e4e5e7 solid;

  ul {
    max-width: 1400px;
    width: 100%;
    display: flex;
    flex-flow: row wrap;
    justify-content: space-evenly;
    margin: 0;
    padding: 0;
    list-style-type: none;

    li {
      display: flex;
      flex-direction: column;
      text-align: center;
      padding: 10px;
    }
  }
}

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
      transition: 0.2s linear;
      margin-top: 10px;
      cursor: pointer;
    }

    @media (hover: hover) {
      button {
        transition: 0.2s linear;
      }

      button:hover {
        background: #f0f2f5;
        color: #45a7f5;
      }
    }

    @media (hover: none) {
      button {
        transition: 0.07s linear;
      }

      button:active {
        background: #f0f2f5;
        color: #45a7f5;
      }
    }
  }
}

section.service-advantages {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 90px 0 90px 0;
  background-color: #f0f2f5;


  .container {
    width: 100%;
    max-width: 1440px;
    box-sizing: border-box;

    .section-title {
      text-align: center;
      font-weight: 500;
      font-size: 55px;
      margin: 40px 0 0 0;

      span {
        color: #42b2fc;
      }
    }

    .content {
      display: flex;
      flex-direction: column;
      align-items: center;
    }
  }
}

footer {
  display: flex;
  flex-direction: row;
  justify-content: center;
  width: 100%;
  padding: 40px;
  background-color: white;

  .container {
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    flex-wrap: wrap;
    width: 100%;
    max-width: 1240px;

    .download {
      padding: 10px;

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

    .social-media {
      display: flex;
      flex-direction: column;
      align-items: flex-end;
      gap: 15px;
      padding: 10px;

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

      img.skolkovo-icon {
        height: 22px;
        width: 68px;
      }
    }
  }
}
</style>