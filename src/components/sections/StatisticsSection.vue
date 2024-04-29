<script setup lang="ts">
import StatisticsItem from '../ui/StatisticsItem.vue';

const statisticsItems = [
    {
        title: '270 000+',
        definition: 'человек нашли своего психолога онлайн',
        width: 'width-280px',
    },
    {
        title: '4 100',
        definition: 'проверенных специалистов',
        width: 'width-140px',
    },
    {
        title: '7 лет',
        definition: 'средний опыт практики',
        width: 'width-140px',
    },
    {
        title: '81%',
        definition: 'клиентов чувствуют результат после 5-й сессии',
        width: 'width-280px',
    },
];
</script>

<template>
    <div class="statistics">
        <ul>
            <li v-for="(item, index) in statisticsItems">
                <StatisticsItem
                    :key="index"
                    :title="item.title"
                    :definition="item.definition"
                    :width="item.width"
                />
            </li>
        </ul>
    </div>
</template>

<style scoped lang="scss">
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
</style>
