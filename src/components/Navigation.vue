<template>
    <div class="navigation aspect-[1/1] w-[98%] rounded-[4vw] sm:w-[85%] sm:rounded-[3.5vw] md:w-[70%] md:rounded-[3vw] lg:w-[50%] lg:rounded-[2.3vw] xl:w-[40%] xl:rounded-[2vw] 2xl:w-[35%] 2xl:rounded-[1.8vw] backdrop-blur-2xl">
        <div class="head rounded-[4vw] sm:rounded-[3.5vw] md:rounded-[3vw] lg:rounded-[2.3vw] xl:rounded-[2vw] 2xl:rounded-[1.5vw]">
            <span class="close text-[9vw] mr-[4.5vw] sm:text-[8vw] sm:mr-[4vw] md:text-[7vw] md:mr-[3.5vw] lg:text-[5vw] lg:mr-[2.5vw] xl:text-[4vw] xl:mr-[2vw] 2xl:text-[3.5vw] 2xl:mr-[1.5vw]" @click="closeNavigation('closeNavigation')">&#215;</span>
        </div>
        
        <div class="gridWindow">
            <div class="window aspect-[1/1.1] w-[63%] rounded-[2.5vw] text-[3.2vw] sm:rounded-[2.3vw] sm:text-[2.8vw] md:rounded-[2vw] md:text-[2.3vw] lg:rounded-[1.5vw] lg:text-[1.8vw] xl:rounded-[1.2vw] xl:text-[1.3vw] 2xl:rounded-[1vw] 2xl:text-[1.2vw]" @click="closeNavigation('aboutMe')">
                <img src="../assets/navigation/author.png" class="w-[43%]">
                <div class="flex flex-col items-center justify-center">
                    <p>Обо Мне</p>
                </div>
            </div>

            <div class="window aspect-[1/1.1] w-[63%] rounded-[2.5vw] text-[3.2vw] sm:rounded-[2.3vw] sm:text-[2.8vw] md:rounded-[2vw] md:text-[2.3vw] lg:rounded-[1.5vw] lg:text-[1.8vw] xl:rounded-[1.2vw] xl:text-[1.3vw] 2xl:rounded-[1vw] 2xl:text-[1.2vw]" @click="closeNavigation('myCertificates')">
                <img src="../assets/navigation/sertifikates.png" class="w-[40%]">
                <div class="flex flex-col items-center justify-center">
                    <p>Мои</p>
                    <p>Сертификаты</p>
                </div>
            </div>

            <div class="window aspect-[1/1.1] w-[63%] rounded-[2.5vw] text-[3.2vw] sm:rounded-[2.3vw] sm:text-[2.8vw] md:rounded-[2vw] md:text-[2.3vw] lg:rounded-[1.5vw] lg:text-[1.8vw] xl:rounded-[1.2vw] xl:text-[1.3vw] 2xl:rounded-[1vw] 2xl:text-[1.2vw]" @click="closeNavigation('myApplications')">
                <img src="../assets/navigation/applications.png" class="w-[40%]">
                <div class="flex flex-col items-center justify-center">
                    <p>Мои</p>
                    <p>Приложения</p>
                </div>
            </div>

            <div class="window aspect-[1/1.1] w-[63%] rounded-[2.5vw] text-[3.2vw] sm:rounded-[2.3vw] sm:text-[2.8vw] md:rounded-[2vw] md:text-[2.3vw] lg:rounded-[1.5vw] lg:text-[1.8vw] xl:rounded-[1.2vw] xl:text-[1.3vw] 2xl:rounded-[1vw] 2xl:text-[1.2vw]" @click="closeNavigation('mySkills')">
                <img src="../assets/navigation/info.png" class="w-[48%]">
                <div class="flex flex-col items-center justify-center">
                    <p>Информация</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
    import { defineEmits} from 'vue';
    const emit = defineEmits(['closeNavigation']);

    const closeNavigation = (txt) => {
        emit('closeNavigation', txt);
    };
</script>

<style scoped>
    .navigation {
        position: absolute;
        display: flex;
        justify-content: center;
        align-items: center;

        background-color: rgba(0, 0, 0, 0.3);

        outline: 3px solid rgba(245, 245, 245, 0.3);
    }

    .head {
        display: flex;
        justify-content: flex-end;
        align-items: center;

        position: fixed;
        top: 0;
        left: 0;

        width: 100%;
        height: 12%;
    }

    .close {
        cursor: pointer;

        color: rgba(245, 245, 245, 0.4);

        font-weight: 100;
        font-family: 'Corbel Light';
        line-height: 0.7;
    }

    .close:hover {
        color: whitesmoke;
    }

    .gridWindow {
        display: inline-grid;
        grid-template-columns: repeat(2, 1fr);
        grid-template-rows: repeat(2, 1fr);
        justify-items: center;
        align-items: center;

        width: 85%;
        aspect-ratio: 1 / 1;
    }

    .window {
        cursor: pointer;

        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: space-evenly;

        box-shadow: 
            3px 3px 4px rgba(0, 0, 0, 0.6),
            -3px -3px 4px rgba(255, 255, 255, 0.3);
    }

    .window:hover {
        background-color: rgba(0, 0, 0, 0.1);
        outline: 1px solid rgba(255, 255, 255, 0.3);
    }

    .window > img {
        opacity: 1;
    }

    .window > div > p {
        color: rgba(255, 255, 255, 0.9);

        font-family: 'Corbel Light';

        text-align: center;
        line-height: 1.2;
    }
</style>
