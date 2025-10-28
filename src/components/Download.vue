<template>
    <div class="download aspect-[1/1.25] w-[99%] rounded-[4vw] sm:w-[90%] sm:rounded-[3.5vw] md:w-[70%] md:rounded-[3vw] lg:w-[45%] lg:rounded-[2.3vw] xl:w-[30%] xl:rounded-[1.5vw] 2xl:w-[28%] 2xl:rounded-[1.3vw] backdrop-blur-md">
        <div class="head rounded-[4vw] sm:rounded-[3.5vw] md:rounded-[3vw] lg:rounded-[2.3vw] xl:rounded-[2vw] 2xl:rounded-[1.5vw]">
            <span class="close text-[9vw] mr-[5vw] sm:text-[8.5vw] sm:mr-[4.5vw] md:text-[7vw] md:mr-[3.5vw] lg:text-[5vw] lg:mr-[2.5vw] xl:text-[3.2vw] xl:mr-[1.5vw] 2xl:text-[3vw] 2xl:mr-[1.3vw]" @click="closeDownload('closeDownload')">&#215;</span>
        </div>

        <div class="application flex items-center justify-center">
            <iframe class="aspect-[1/1.464] frame w-[86%] rounded-[3vw] sm:rounded-[2.5vw] md:rounded-[2vw] lg:rounded-[1.5vw] xl:rounded-[1vw] 2xl:rounded-[1.5vw]" src="https://cozy-douhua-274f99.netlify.app/"></iframe>
        </div>

        <div class="windowsLoading flex items-center">
            <div class="windows flex items-center justify-center w-1/3 h-full rounded-bl-[4vw] sm:rounded-bl-[3.5vw] md:rounded-bl-[3vw] lg:rounded-bl-[2.3vw] xl:rounded-bl-[1.5vw] 2xl:rounded-bl-[1.3vw]">
                <a href="https://github.com/GlebGorlanov/git_test/releases/download/v1.0.0/Calculator.Setup.1.0.0.exe" download class="flex items-center justify-center w-full h-full">
                    <span class="text-[4vw] sm:text-[3.8vw] md:text-[3vw] lg:text-[2vw] xl:text-[1.5vw] 2xl:text-[1.3vw]">Windows</span><img src="../assets/applications/zagruzka.png" class="w-[15%] ml-[10%] sm:w-[14.5%] sm:ml-[9%] md:w-[14%] md:ml-[6%] lg:w-[13%] lg:ml-[5%] xl:w-[12%] xl:ml-[5%] 2xl:w-[12%] 2xl:ml-[5%]">
                </a>
            </div>

            <div class="linux flex items-center justify-center w-1/3 h-full">
                <a href="#" class="flex items-center justify-center w-full h-full">
                    <span class="text-[4vw] sm:text-[3.8vw] md:text-[3vw] lg:text-[2vw] xl:text-[1.5vw] 2xl:text-[1.3vw]">Linux</span><img src="../assets/applications/zagruzka.png" class="w-[15%] ml-[10%] sm:w-[14.5%] sm:ml-[9%] md:w-[14%] md:ml-[6%] lg:w-[13%] lg:ml-[5%] xl:w-[12%] xl:ml-[5%] 2xl:w-[12%] 2xl:ml-[5%]">
                </a>
            </div>

            <div class="macos flex items-center justify-center w-1/3 h-full rounded-br-[4vw] sm:rounded-br-[3.5vw] md:rounded-br-[3vw] lg:rounded-br-[2.3vw] xl:rounded-br-[1.5vw] 2xl:rounded-br-[1.3vw]">
                <a href="#" class="flex items-center justify-center w-full h-full">
                    <span class="text-[4vw] sm:text-[3.8vw] md:text-[3vw] lg:text-[2vw] xl:text-[1.5vw] 2xl:text-[1.3vw]">MacOS</span><img src="../assets/applications/zagruzka.png" class="w-[15%] ml-[10%] sm:w-[14.5%] sm:ml-[9%] md:w-[14%] md:ml-[6%] lg:w-[13%] lg:ml-[5%] xl:w-[12%] xl:ml-[5%] 2xl:w-[12%] 2xl:ml-[5%]">
                </a>
            </div>
        </div>
    </div>
</template>

<script setup>
    import { defineEmits } from 'vue';
    const emit = defineEmits(['closeDownload']);

    const closeDownload = (txt) => {
        emit('closeDownload', txt);
    };
</script>

<style scoped>
    .download {
        position: absolute;

        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;

        background-color: rgba(168, 168, 168, 0.3);

        outline: 2px solid rgba(255, 255, 255, 0.4);

        z-index: 10;
    }

    .head {
        display: flex;
        justify-content: flex-end;
        align-items: center;

        width: 100%;
        height: 10%;
    }

    .close {
        cursor: pointer;

        color: rgba(245, 245, 245, 0.5);

        font-weight: 100;
        font-family: 'Corbel Light';
        line-height: 0.7;
    }

    .close:hover {
        color: whitesmoke;
    }

    .application {
        width: 100%;
        height: 100%;
    }

    .windowsLoading {
        width: 100%;
        height: 10%;
    }

    .windowsLoading > div {
        cursor: pointer;

        color: white;
        background-color: rgba(0, 0, 0, 0.5);

        border-top: 1px groove rgba(255, 255, 255, 0.8);

        font-family: 'Corbel Light';
        font-weight: 100;
    }

    .windowsLoading > div:hover {
        background-color: rgba(0, 0, 0, 0.6);
    }

    .windowsLoading > div > a > img {
        opacity: 0.6;
    }

    .linux {
        border-left: 1px solid rgba(255, 255, 255, 0.5);
        border-right: 1px solid rgba(255, 255, 255, 0.5);
    }
</style>


