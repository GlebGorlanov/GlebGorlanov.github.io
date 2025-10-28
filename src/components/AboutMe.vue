<template>
    <div class="aboutMe aspect-[1/0.9] w-[98%] rounded-[4vw] sm:w-[90%] sm:rounded-[3.5vw] md:w-[68%] md:rounded-[3vw] lg:w-[55%] lg:rounded-[2.3vw] xl:w-[45%] xl:rounded-[2vw] 2xl:w-[40%] 2xl:rounded-[1.8vw] backdrop-blur-2xl">
        <div class="head rounded-[4vw] sm:rounded-[3.5vw] md:rounded-[3vw] lg:rounded-[2.3vw] xl:rounded-[2vw] 2xl:rounded-[1.5vw]">
            <span class="back text-[6.3vw] ml-[4.5vw] sm:text-[5.5vw] sm:ml-[4vw] md:text-[4.5vw] md:ml-[3.5vw] lg:text-[3.8vw] lg:ml-[2.4vw] xl:text-[3vw] xl:ml-[2vw] 2xl:text-[2.6vw] 2xl:ml-[1.5vw]" @click="closeAboutMe('backAboutMe')" :style="{color:color}">&#8592;</span>
            <span class="close text-[8vw] mr-[4.5vw] sm:text-[7.5vw] sm:mr-[4vw] md:text-[6.3vw] md:mr-[3.5vw] lg:text-[4.8vw] lg:mr-[2.4vw] xl:text-[4vw] xl:mr-[2vw] 2xl:text-[3.5vw] 2xl:mr-[1.5vw]" @click="closeAboutMe('closeAboutMe')">&#215;</span>
        </div>

        <div class="scrollWindow">
            <div class="fotoBox flex justify-center items-center shrink-0">
                <ul class="flex justify-around items-center w-[90%]">
                    <li><button class="button w-[12vw] text-[5vw] sm:w-[11vw] sm:text-[4.5vw] md:w-[9.5vw] md:text-[4vw] lg:w-[7.5vw] lg:text-[3.5vw] xl:w-[5.5vw] xl:text-[2.5vw] 2xl:w-[5vw] 2xl:text-[2vw]" @click="change('<')"><</button></li>
                    <li class="flex justify-center"><img :src="images[indexImage]" :class="foto" @click="enlargePhoto"></li>
                    <li><button class="button w-[12vw] text-[5vw] sm:w-[11vw] sm:text-[4.5vw] md:w-[9.5vw] md:text-[4vw] lg:w-[7.5vw] lg:text-[3.5vw] xl:w-[5.5vw] xl:text-[2.5vw] 2xl:w-[5vw] 2xl:text-[2vw]" @click="change('>')">></button></li>
                </ul>
            </div>

            <div class="info flex items-center justify-center shrink-0">
                <ul class="list text-[3.8vw] sm:text-[3.2vw] md:text-[2.5vw] lg:text-[2vw] xl:text-[1.6vw] 2xl:text-[1.4vw]">
                    <li><span class="headText text-[4vw] sm:text-[3.6vw] md:text-[3vw] lg:text-[2.3vw] xl:text-[1.8vw] 2xl:text-[1.6vw]">Ф.И.О.</span><img src="../assets/aboutMe/person.png" class="w-[6%] mx-[2%] inline align-middle"><span class="text">Горланов Глеб Сергеевич</span></li>
                    <li><span class="headText text-[4vw] sm:text-[3.6vw] md:text-[3vw] lg:text-[2.3vw] xl:text-[1.8vw] 2xl:text-[1.6vw]">Направление:</span><img src="../assets/aboutMe/kompas.png" class="w-[6%] mx-[2%] inline align-middle"><span class="text">Фронтенд Разработка</span></li>
                    <li><span class="headText text-[4vw] sm:text-[3.6vw] md:text-[3vw] lg:text-[2.3vw] xl:text-[1.8vw] 2xl:text-[1.6vw]">Адрес:</span><img src="../assets/aboutMe/flag.png" class="w-[6%] mx-[2%] inline align-middle"><span class="text">Россия г.Ярославль</span></li>
                    <li><span class="headText text-[4vw] sm:text-[3.6vw] md:text-[3vw] lg:text-[2.3vw] xl:text-[1.8vw] 2xl:text-[1.6vw]">Почта:</span><img src="../assets/aboutMe/mail.png" class="w-[8%] mx-[1%] inline align-middle"><span class="mailForm"><span class="mail">gorlanovgleb</span><span class="text-pink-300">@</span><span class="text-blue-300 font-thin">gmail</span><span class="mail">.com</span></span><span class="copyText ml-[3%] aspect-[1/1.3] w-[4.5vw] text-[3.5vw] sm:w-[4vw] sm:text-[3vw] md:w-[3.5vw] md:text-[2.6vw] lg:w-[3vw] lg:text-[2.3vw] xl:w-[2.5vw] xl:text-[2vw] 2xl:w-[2vw] 2xl:text-[1.6vw] inline align-middle" @click="copyText('gorlanovgleb@gmail.com', '&#10003;')">{{ txt }}</span></li>
                    <li><span class="headText text-[4vw] sm:text-[3.6vw] md:text-[3vw] lg:text-[2.3vw] xl:text-[1.8vw] 2xl:text-[1.6vw]">Телефон:</span><img src="../assets/aboutMe/phone.png" class="w-[9%] mx-[2%] inline align-middle"><span class="phone">8 903 *** ** **</span></li>
                    <li>
                        <span class="headText text-[4vw] sm:text-[3.6vw] md:text-[3vw] lg:text-[2.3vw] xl:text-[1.8vw] 2xl:text-[1.6vw]">Образование:</span><img src="../assets/aboutMe/lamp.png" class="w-[9%] mx-[1%] inline align-middle"><span class="text">Профессиональное училище №27 
                        г.Ярославля Cпециальность "Социальный Работник"</span>
                    </li>
                    <li>
                        <span class="headText text-[4vw] sm:text-[3.6vw] md:text-[3vw] lg:text-[2.3vw] xl:text-[1.8vw] 2xl:text-[1.6vw]">Образование:</span><img src="../assets/aboutMe/lamp.png" class="w-[9%] mx-[1%] inline align-middle"><span class="text">Ярославское медицинское училище
                        Министерства путей сообщения России
                        Специальность "Стоматология" квалификация
                        <img src="../assets/aboutMe/redCross.png" class="w-[7%] mx-[1%] inline align-middle">"Зубной врач"</span>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script setup>
    import { ref, defineEmits, defineProps, onMounted, onUnmounted } from 'vue';
    
    const props = defineProps(['aboutMe']);
    const emit = defineEmits(['closeAboutMe']);

    const closeAboutMe = (txt) => {
        emit('closeAboutMe', txt);
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

    const indexImage = ref(0);
    const images = ref([
        new URL('../assets/images/foto.jpg', import.meta.url).href,
        new URL('../assets/images/foto1.jpg', import.meta.url).href,
        new URL('../assets/images/foto2.jpg', import.meta.url).href,
    ]);

    const change = (x) => {
        if(x === '>') {
            indexImage.value = (indexImage.value + 1) % images.value.length;
        } else {
            indexImage.value = (indexImage.value - 1 + images.value.length) % images.value.length;
        };
    };

    const foto = ref('foto');

    const enlargePhoto = () => {
        if(foto.value === 'foto') {
            foto.value = 'largePhoto';
        } else {
            foto.value = 'foto';
        };
    };

    const  txt = ref('');
    const copy = ref(false);

    const copyText = (a, b) => {
        navigator.clipboard.writeText(a).then(() => {
            txt.value = b;
            copy.value = true;
            setTimeout(() => {copy.value = false, txt.value = ''}, 2000);
        });
    };
</script>

<style scoped>
    .aboutMe {
        position: absolute;
        display: flex;
        flex-direction: column;

        background-color: rgba(0, 0, 0, 0.3);

        outline: 3px solid rgba(245, 245, 245, 0.3);
        border-bottom-right-radius: 8px;
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

        font-weight: 100;
        font-family: 'Corbel Light';

        line-height: 0.7;
    }

    .scrollWindow {
        display: flex;
        flex-direction: column;

        width: 100%;
        height: 100%;

        overflow-y: auto;
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

    .fotoBox {
        width: 100%;
        flex-basis: 100%;
    }

    .info {
        width: 100%;
        flex-basis: 100%;

        text-align: center;
    }

    .text {
        color: rgb(255, 255, 255, 0.7);

        font-family: 'MADEGoodTimeScript';
        letter-spacing: 1px;
    }

    .list {
        width: 85%;
        padding: 5%;

        background-color: rgba(0, 0, 0, 0.4);

        margin: 5% 0;
        line-height: 1.4;
    }

    .button {
        display: flex;
        justify-content: space-evenly;
        align-items: center;

        aspect-ratio: 1 / 1;

        background-color: rgba(0, 0, 0, 0.5);
        color: whitesmoke;

        border: 1px groove rgba(245, 245, 245, 0.6);
        border-radius: 50%;

        font-family: 'Corbel Light';
        line-height: 0.7;
    }

    button:hover {
        background-color: rgba(0, 0, 0, 0.7);
        border-color: rgba(245, 245, 245, 0.8);
    }


    .foto {
        cursor: pointer;

        width: 80%;
        border: 3px solid rgba(245, 245, 245, 0.3);
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
    
        border: 1px groove rgba(245, 245, 245, 0.6);
    }

    .headText {
        color:rgb(236, 203, 162);

        font-weight: 300;
        font-family: 'Corbel';
        line-height: 0.7;

    }

    .mail {
        font-weight: 100;
        color: rgba(255, 255, 255, 0.8);
    }

    .phone {
        font-weight: 100;
        color: rgb(206, 206, 206);
    }

    .copyText {
        cursor: pointer;
        display: inline-block;

        border: 1px groove rgba(192, 192, 192, 0.6);

        background-color: rgba(192, 192, 192, 0.2);
        color: rgba(255, 255, 255, 0.8);

        box-shadow: 3px -3px 0px 0px rgba(160, 160, 160, 0.4);
    }

    .copyText:hover {
        border: 1px groove rgba(255, 255, 255, 0.7);
    }
</style>
