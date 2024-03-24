<script setup lang="ts">

defineProps<{
    title: string,
    links: {
        name: string,
        linkHref: string
    }[]
}>()

</script>


<template>
    <div class="wrapper">
        <h5>{{ title }}</h5>
        <div class="links">
            <a v-for="(link, index) in links" :href="link.linkHref" :key="index">{{ link.name }}</a>
        </div>
    </div>
</template>


<style scoped lang="scss">
.wrapper {
    padding: 10px;

    h5 {
        font-weight: 500;
        font-size: 14px;
        color: #345066;
    }

    .links {
        margin-top: 3px;
        display: flex;
        flex-direction: column;

        a {
            margin-top: 6px;
            text-decoration: none;
            color: #8497a6;
            font-size: 14px;

            &:hover {
                color: #52626f;
            }
        }
    }
}
</style>