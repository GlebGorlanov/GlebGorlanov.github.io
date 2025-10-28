<template>
    <div class="myApplications w-[98%] aspect-[1/1] rounded-[4vw] sm:w-[90%] sm:aspect-[1/1] sm:rounded-[3.2vw] md:w-[85%] md:aspect-[1/0.85] md:rounded-[2.5vw] lg:w-[75%] lg:aspect-[1/0.8] lg:rounded-[2vw] xl:w-[65%] xl:aspect-[1/0.65] xl:rounded-[1.3vw] 2xl:w-[55%] 2xl:aspect-[1/0.70] 2xl:rounded-[1.5vw] backdrop-blur-2xl">
        <div class="head rounded-[4vw] sm:rounded-[3.5vw] md:rounded-[3vw] lg:rounded-[2.3vw] xl:rounded-[2vw] 2xl:rounded-[1.5vw]">
            <span class="back text-[6.3vw] ml-[4.5vw] sm:text-[5.5vw] sm:ml-[4vw] md:text-[4vw] md:ml-[3vw] lg:text-[3.8vw] lg:ml-[2.4vw] xl:text-[2.6vw] xl:ml-[2vw] 2xl:text-[2.3vw] 2xl:ml-[2vw]" @click="closeMyApplications('backMyApplications')" :style="{color:color}">&#8592;</span>
            <span class="close text-[9vw] mr-[4.5vw] sm:text-[8vw] sm:mr-[4vw] md:text-[6.5vw] md:mr-[3vw] lg:text-[5vw] lg:mr-[2.5vw] xl:text-[4vw] xl:mr-[2vw] 2xl:text-[3.5vw] 2xl:mr-[2vw]" @click="closeMyApplications('closeMyApplications')">&#215;</span>
        </div>

        <div class="applications flex items-center justify-center">
            <div class="gridWindow w-[95%] h-[95%] lg:w-[90%] xl:w-[85%]">
                <div class="window w-[90%] sm:w-[85%] md:w-[80%] lg:w-[75%] xl:w-[70%]" @click="closeMyApplications('download')">
                    <img src="../assets/applications/calculator.png" class="w-[100%]">
                    <div class="flex items-center justify-center">
                        <p class="text-[3vw] sm:text-[2.8vw] md:text-[2.1vw] lg:text-[1.9vw] xl:text-[1.2vw] 2xl:text-[1vw]">Calculator</p>
                    </div>
                </div>

                <div class="window w-[90%] sm:w-[85%] md:w-[80%] lg:w-[75%] xl:w-[70%]" @click="closeMyApplications('download')">
                    <img src="../assets/applications/cross_zero.png" class="w-[100%]">
                    <div class="flex items-center justify-center">
                        <p class="text-[3vw] sm:text-[2.8vw] md:text-[2.1vw] lg:text-[1.9vw] xl:text-[1.2vw] 2xl:text-[1vw]">Cross_Zero</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
    import { ref, defineEmits, onMounted, onUnmounted } from 'vue';
    const emit = defineEmits(['closeMyApplications']);

    const closeMyApplications = (txt) => {
        emit('closeMyApplications', txt);
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
    .myApplications {
        position: absolute;

        background-color: rgba(0, 0, 0, 0.3);
        outline: 3px solid rgba(245, 245, 245, 0.3);
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

        color: rgba(255, 255, 255, 0.4);

        font-weight: 100;
        font-family: 'Corbel Light';
        line-height: 0.7;
    }

    .close:hover {
        color: white;
    }

    .back {
        cursor: pointer;

        color: whitesmoke;

        font-weight: 100;
        font-family: 'Corbel Light';
        line-height: 0.7;
    }

    .applications {
        width: 100%;
        height: 88%;

        /*border-bottom-left-radius: 20px;
        border-bottom-right-radius: 20px;*/

        overflow-x: auto;
    }

    .gridWindow {
        display: inline-grid;
        grid-template-columns: repeat(2, 1fr);
        grid-template-rows: repeat(1, 1fr);
        justify-items: center;
        align-items: center;
    }

    .window {
        cursor: pointer;

        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

        outline: 3px solid rgba(255, 255, 255, 0.3);
        border-radius: 15px;
    }

    .window > img {
        opacity: 1;

        border-top-left-radius: 15px;
        border-top-right-radius: 15px;
    }

    .window > div {
        width: 100%;

        background-color: rgba(0, 0, 0, 0.3);

        border-bottom-right-radius: 15px;
        border-bottom-left-radius: 15px;
    }

    .window > div > p {
        color: whitesmoke;
        
        font-family: 'Corbel Light';

        text-align: center;
        line-height: 2.0;
        letter-spacing: 1px;
    }
</style>
