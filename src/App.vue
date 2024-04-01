<script setup lang="ts">
import CoverSection from './components/CoverSection.vue'
import StatisticsItem from './components/StatisticsItem.vue'
import HelpWithWhatSection from './components/HelpWithWhatSection.vue'
import Advantage from './components/Advantage.vue'
import FooterSection from './components/FooterSection.vue'
// import FooterLinksItem from './components/FooterLinksItem.vue'

const statisticsItems = [
  {
    title: '270 000+',
    definition: 'человек нашли своего психолога онлайн',
    width: 'width-280px'
  },
  {
    title: '4 100',
    definition: 'проверенных специалистов',
    width: 'width-140px'
  },
  {
    title: '7 лет',
    definition: 'средний опыт практики',
    width: 'width-140px'
  },
  {
    title: '81%',
    definition: 'клиентов чувствуют результат после 5-й сессии',
    width: 'width-280px'
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
</script>

<template>
  <div class="header-container">
    <div class="header">
      <a href="#" class="title">ЯСНО</a>
      <a href="#help-with-what" class="help-with-what-anchor">С чем поможет психолог?</a>
    </div>
  </div>

  <CoverSection />

  <div class="statistics">
    <ul>
      <li v-for="(item, index) in statisticsItems">
        <StatisticsItem :key="index" :title="item.title" :definition="item.definition" :width="item.width" />
      </li>
    </ul>
  </div>

  <HelpWithWhatSection />

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

  <FooterSection />
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

    @media(max-width: 925px) {
      padding: 5px 3.3vw;
    }

    .title {
      font-size: 35px;
      color: #42b2fc;
      font-weight: bold;
      text-decoration: none;

      @media(max-width: 925px) {
        font-size: 30px;
      }
    }

    .help-with-what-anchor {
      padding: 10px 0px 10px 10px;
      text-align: end;
      color: black;
      font-size: 16px;
      transition: color 0.3s;
      text-decoration: none;

      @media(hover: hover) {
        &:hover {
          color: #42b2fc;
        }
      }

      @media(hover: none) {
        &:active {
          color: #42b2fc;
        }
      }

      @media(max-width: 925px) {
        font-size: 14px;
      }
    }
  }
}

.statistics {
  width: 100%;
  display: flex;
  flex-direction: row;
  justify-content: center;
  padding: 20px 0;
  border-bottom: 1px #e4e5e7 solid;

  ul {
    max-width: 1400px;
    width: 100%;
    display: grid;
    justify-content: space-evenly;
    grid-template-columns: repeat(4, auto);
    margin: 0;
    padding: 0;
    list-style-type: none;

    @media (max-width: 925px) {
      grid-template: auto auto / 1fr 1fr;
      gap: 30px / 10px;
      margin-left: 10px;
    }

    li {
      display: flex;
      flex-direction: column;
      text-align: center;
      padding: 10px;
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
</style>