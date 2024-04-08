<template>
    <div class="header">
        <div class="container">
            <a href="#" class="title">ЯСНО</a>
            <a href="#help-with-what" class="help-with-what-anchor">С чем поможет психолог?</a>
        </div>
    </div>
</template>


<style scoped lang="scss">
.header {
    display: flex;
    justify-content: center;
    width: 100%;

    .container {
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
</style>