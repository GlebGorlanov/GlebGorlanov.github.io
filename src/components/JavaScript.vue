<template>
    <div class="javaScript w-[98%] aspect-[1/1.3] rounded-[4vw] sm:w-[95%] sm:aspect-[1/0.65] sm:rounded-[3.5vw] md:w-[85%] md:rounded-[3vw] lg:w-[75%] lg:rounded-[2.3vw] xl:w-[70%] xl:aspect-[1/0.6] xl:rounded-[2vw] 2xl:w-[60%] 2xl:rounded-[1.8vw] backdrop-blur-2xl">
        <div class="head rounded-[4vw] sm:rounded-[3.5vw] md:rounded-[3vw] lg:rounded-[2.3vw] xl:rounded-[2vw] 2xl:rounded-[1.5vw]">
            <span class="back text-[6.3vw] ml-[4.5vw] sm:text-[5.5vw] sm:ml-[4vw] md:text-[4.5vw] md:ml-[3.5vw] lg:text-[3.8vw] lg:ml-[2.4vw] xl:text-[3vw] xl:ml-[2vw] 2xl:text-[2.6vw] 2xl:ml-[1.5vw]" @click="closeJavaScript('backJavaScript')" :style="{color:color}">&#8592;</span>
            <span class="close text-[9vw] mr-[4.5vw] sm:text-[8vw] sm:mr-[4vw] md:text-[7vw] md:mr-[3.5vw] lg:text-[5vw] lg:mr-[2.5vw] xl:text-[4vw] xl:mr-[2vw] 2xl:text-[3.5vw] 2xl:mr-[1.5vw]" @click="closeJavaScript('closeJavaScript')">&#215;</span>
        </div>

        <div class="certificates flex justify-center">
            <div class="gridWindow w-[95%]">
                <div v-for="(src, index) in sertificates" :key="index" class="window w-[95%]">
                    <img :src="src" :class="fotoClasses[index]" @click="enlargePhoto(index)">
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
    import {ref, defineEmits, onMounted, onUnmounted} from 'vue';
    const emit = defineEmits(['closeJavaScript']);

    const closeJavaScript = (txt) => {
        emit('closeJavaScript', txt);
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

    const sertificates = ref([
        new URL('../assets/JavaScript/freeCodeCamp JavaScript.png', import.meta.url).href,
        new URL('../assets/JavaScript/Stepik JavaScript.jpg', import.meta.url).href,
        new URL('../assets/JavaScript/Stepik Dive into JavaScript for Beginners.jpg', import.meta.url).href,
        new URL('../assets/JavaScript/Udemy JavaScript 1.jpg', import.meta.url).href,
        new URL('../assets/JavaScript/Udemy JavaScript 2.jpg', import.meta.url).href,
        new URL('../assets/JavaScript/SoloLearn Introduction to JavaScript.jpg', import.meta.url).href,
        new URL('../assets/JavaScript/SoloLearn JavaScript Intermediate.jpg', import.meta.url).href,
        new URL('../assets/JavaScript/SoloLearn JavaScript.jpg', import.meta.url).href,
    ]);

    const fotoClasses = ref(Array(sertificates.value.length).fill('foto'));

    const enlargePhoto = (index) => {
        fotoClasses.value[index] = fotoClasses.value[index] === 'foto'? 'largePhoto': 'foto';
    };
</script>

<style scoped>
    .javaScript {
        position: absolute;

        background-color: rgba(0, 0, 0, 0.4);
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

        color: whitesmoke;

        font-weight: 100;
        font-family: 'Corbel Light';
        line-height: 0.7;
    }

    .certificates {
        width: 100%;
        height: 88%;

        overflow-x: auto;
    }

    .certificates::-webkit-scrollbar {
        width: 8px;
    }

    .certificates::-webkit-scrollbar-track {
        border-radius: 8px;
    }

    .certificates::-webkit-scrollbar-thumb {
        background-color: rgba(192, 192, 192, 0.5);
        border-radius: 8px;
    }

    .certificates::-webkit-scrollbar-thumb:hover {
        background-color: rgba(245, 245, 245, 0.6);
    }

    @media(max-width: 640px) {
        .gridWindow {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            grid-template-rows: repeat(3, 1fr);
            justify-items: center;
            align-items: center;
        }
    }

    @media(min-width: 640px) {
        .gridWindow {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            grid-template-rows: repeat(2, 1fr);
            justify-items: center;
            align-items: center;
        }
    }

    .foto {
        cursor: pointer;
        
        width: 100%;
        border: 3px solid rgba(255, 255, 255, 0.4);

        margin-bottom: 5%;
    }

    .largePhoto {
        cursor: pointer;

        display: flex;
        justify-content: center;
        align-items: center;

        position: absolute;
        top: 50%;
        left: 50%;
        width: 100%;
        transform: translate(-50%, -50%);
        z-index: 50;
    
        border: 3px solid rgba(245, 245, 245, 0.6);
    }
</style>
