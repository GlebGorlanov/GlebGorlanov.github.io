<template>
    <div class="developer w-full h-[90vh] md:w-[90%] backdrop-blur-xl">
        <div class="image flex justify-around items-center">
            <span class="oneSpan w-[14%] sm:w-[12%] md:w-[11%] lg:w-[9%] xl:w-[6.5%] 2xl:w-[6%]"><img src="../assets/header/home.png" class="iconHome" :class="changeClass" @click="openNavigation('navigation')"></span>
            <span class="w-[14%] sm:w-[12%] md:w-[11%] lg:w-[9%] xl:w-[6.5%] 2xl:w-[6%]"><img src="../assets/developers/html.png" class="icon"></span>
            <span class="w-[14%] sm:w-[12%] md:w-[11%] lg:w-[9%] xl:w-[6.5%] 2xl:w-[6%]"><img src="../assets/developers/css.png" class="icon"></span>
            <span class="w-[14%] sm:w-[12%] md:w-[11%] lg:w-[9%] xl:w-[6.5%] 2xl:w-[6%]"><img src="../assets/developers/js.png" class="icon"></span>
        </div>

        <div class="headText w-[90%] h-[50%]">
            <p class="leading-[0.8] text-[14vw] sm:text-[13vw] md:text-[10vw] lg:text-[9vw] xl:text-[8vw] 2xl:text-[8.5vw]">Frontend Development</p>
            <div class="txtWrap w-[60%] h-[25%] flex justify-center items-center">
                <p class="txt leading-[1.3] text-[4.5vw] sm:text-[3.8vw] md:text-[3.5vw] lg:text-[3vw] xl:text-[2.4vw] 2xl:text-[2.3vw]">Html. Css. JavaScript. Vue. TailWind. Git.</p>
            </div>
        </div>

        <div class="image flex justify-around items-center">
            <span class="w-[14%] sm:w-[12%] md:w-[11%] lg:w-[9%] xl:w-[6.5%] 2xl:w-[6%]"><img src="../assets/developers/tailwind.png" class="icon"></span>
            <span class="w-[14%] sm:w-[12%] md:w-[11%] lg:w-[9%] xl:w-[6.5%] 2xl:w-[6%]"><img src="../assets/developers/vue.png" class="icon"></span>
            <span class="w-[14%] sm:w-[12%] md:w-[11%] lg:w-[9%] xl:w-[6.5%] 2xl:w-[6%]"><img src="../assets/developers/python.png" class="icon"></span>
            <span class="w-[14%] sm:w-[12%] md:w-[11%] lg:w-[9%] xl:w-[6.5%] 2xl:w-[6%]"><img src="../assets/developers/github.png" class="icon"></span>
        </div>
    </div>
</template>

<script setup>
    import { ref, defineEmits, onMounted, onUnmounted } from 'vue';
    const emit = defineEmits(['navigation']);

    const openNavigation = (txt) => {
        emit('navigation', txt);
    };

    const changeClass = ref('imgOne');
    let time = null;

    onMounted(() => {
        time = setInterval(() => {
            changeClass.value = changeClass.value === 'imgOne'? 'imgTwo': 'imgOne';
        }, 1000);
    });

    onUnmounted(() => {
        clearInterval(time);
    });
</script>

<style scoped>
    .developer {
        position: absolute;

        display: flex;
        flex-direction: column;
        justify-content: space-around;
        align-items: center;

        background-color: rgba(0, 0, 0, 0.1);
    }

    .headText {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

        color: rgba(214, 214, 214, 0.8);

        font-family: 'MADEGoodTimeScript';
        text-align: center;
    }

    .txt {
        font-family: 'Corbel Light';
        font-weight: 100;
    }

    .image {
        width: 90%;
        height: 25%;
    }

    .image > span {
        display: flex;
        justify-content: center;
        align-items: center;

        padding: 10px;
        
        box-shadow: inset -3px -3px 4px rgba(255, 255, 255, 0.3), 
        inset 3px 3px 4px rgba(70, 70, 70, 0.7);
    }

    .icon {
        opacity: 0.5;
        filter: grayscale(100%);
    }

    .imgOne {
        opacity: 1;
        filter: grayscale(0%);
    }

    .imgTwo {
        opacity: 0.6;
        filter: grayscale(100%);
    }

    .iconHome {
        cursor: pointer;
    }

    .oneSpan:hover {
        box-shadow: 
            3px 3px 4px rgba(0, 0, 0, 0.6),
            -3px -3px 4px rgba(255, 255, 255, 0.3);
        
        border-radius: 10px;
    }
</style>
