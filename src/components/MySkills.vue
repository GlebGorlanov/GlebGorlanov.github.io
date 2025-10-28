<template>
    <div class="mySkills w-[98%] aspect-[1/1.1] rounded-[4vw] sm:w-[95%] sm:aspect-[1/0.7] sm:rounded-[3.5vw] md:w-[85%] md:rounded-[3vw] lg:w-[75%] lg:rounded-[2.3vw] xl:w-[70%] xl:aspect-[1/0.55] xl:rounded-[2vw] 2xl:w-[60%] 2xl:rounded-[1.8vw] backdrop-blur-2xl">
        <div class="head rounded-[4vw] sm:rounded-[3.5vw] md:rounded-[3vw] lg:rounded-[2.3vw] xl:rounded-[2vw] 2xl:rounded-[1.5vw]">
            <span class="back text-[6.3vw] ml-[4.5vw] sm:text-[5.5vw] sm:ml-[4vw] md:text-[4.5vw] md:ml-[3.5vw] lg:text-[3.8vw] lg:ml-[2.4vw] xl:text-[3vw] xl:ml-[2vw] 2xl:text-[2.6vw] 2xl:ml-[1.5vw]" @click="closeMySkills('backMySkills')" :style="{color:color}">&#8592;</span>
            <span class="close text-[9vw] mr-[4.5vw] sm:text-[8vw] sm:mr-[4vw] md:text-[7vw] md:mr-[3.5vw] lg:text-[5vw] lg:mr-[2.5vw] xl:text-[4vw] xl:mr-[2vw] 2xl:text-[3.5vw] 2xl:mr-[1.5vw]" @click="closeMySkills('closeMySkills')">&#215;</span>
        </div>

        <div class="scrollWindow">
            <div class="message flex flex-col items-center justify-center">
                <ul class="list text-[5vw] sm:text-[4.5vw] md:text-[3.8vw] lg:text-[3.2vw] xl:text-[2vw] 2xl:text-[1.8vw]">
                    <li>Сайт - Портфолио создан на:</li>
                    <li>Html, Css, JavaScript, Vue, TailWind</li>
                    <li>Автор: Горланов Глеб С. Россия, г.Ярославль</li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script setup>
    import { ref, defineEmits, onMounted, onUnmounted } from 'vue';
    const emit = defineEmits(['closeMySkills']);

    const closeMySkills = (txt) => {
        emit('closeMySkills', txt);
    };

    const color = ref('rgba(245, 245, 245, 0.5)');
    let time = null;

    onMounted(() => {
        time = setInterval(() => {
            color.value = color.value === 'rgba(245, 245, 245, 0.5)'? 'rgba(245, 245, 245, 1)': 'rgba(245, 245, 245, 0.5)';
        }, 1000);
    });

    onUnmounted(() => {
        clearInterval(time);
    });
</script>

<style scoped>
    .mySkills {
        display: flex;
        flex-direction: column;

        position: absolute;

        background-color: rgba(0, 0, 0, 0.3);

        outline: 3px solid rgba(245, 245, 245, 0.3);
        border-bottom-right-radius: 10px;
    }

    .head {
        display: flex;
        justify-content: space-between;
        align-items: center;

        width: 100%;
        height: 12%;
    }

    .close {
        cursor: pointer;

        color: rgba(245, 245, 245, 0.6);

        font-weight: 100;
        font-family: 'Corbel Light';
        line-height: 0.7;
    }

    .close:hover {
        color: whitesmoke;
    }

    .back {
        cursor: pointer;

        color: rgba(245, 245, 245, 0.6);

        font-weight: 100;
        font-family: 'Corbel Light';
        line-height: 0.7;
    }

    .scrollWindow {
        width: 100%;
        height: 100%;

        overflow-x: auto;
    }

    .scrollWindow::-webkit-scrollbar {
        width: 8px;
    }

    .scrollWindow::-webkit-scrollbar-track {
        border-radius: 8px;
    }

    .scrollWindow::-webkit-scrollbar-thumb {
        background-color: rgba(192, 192, 192, 0.5);
        border-radius: 8px;
    }

    .scrollWindow::-webkit-scrollbar-thumb:hover {
        background-color: rgba(245, 245, 245, 0.6);
    }

    .message {
        width: 100%;
        height: 100%;
    }

    .list {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

        width: 85%;
        height: 50%;

        color: rgba(255, 255, 255, 0.8);
        background-color: rgba(0, 0, 0, 0.4);

        font-family: 'Corbel Light';
        line-height: 1.5;
        text-align: center;
    }
</style>
