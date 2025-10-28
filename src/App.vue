<template>
    <div class="headWindow flex flex-col items-center justify-center">
        <div class="content flex items-center justify-center w-full h-[90%]">
            <Developer v-show="developer" @navigation="openNavigation"/>
            <Navigation v-show="navigation" @closeNavigation="openNavigation"/>
            <AboutMe v-show="aboutMe" @closeAboutMe="openNavigation" :aboutMe="aboutMe"/>
            <MyCertificates v-show="myCertificates" @closeMyCertificates="openNavigation"/>
            <HtmlCss v-show="htmlCss" @closeHtmlCss="openNavigation"/>
            <JavaScript v-show="javaScript" @closeJavaScript="openNavigation"/>
            <Python v-show="python" @closePython="openNavigation"/>
            <Others v-show="others" @closeOthers="openNavigation"/>
            <MyApplications v-show="myApplications" @closeMyApplications="openNavigation"/>
            <Download v-show="download" @closeDownload="openNavigation"/>
            <MySkills v-show="mySkills" @closeMySkills="openNavigation"/>
        </div>
    </div>
</template>

<script setup>
    import Developer from './components/Developer.vue';
    import Navigation from './components/Navigation.vue';
    import AboutMe from './components/AboutMe.vue';
    import MyCertificates from './components/MyCertificates.vue';
    import HtmlCss from './components/HtmlCss.vue';
    import JavaScript from './components/JavaScript.vue';
    import Python from './components/Python.vue';
    import Others from './components/Others.vue';
    import MyApplications from './components/MyApplications.vue';
    import Download from './components/Download.vue';
    import MySkills from './components/MySkills.vue';

    import {ref} from 'vue';
    const developer = ref(true);
    const navigation = ref(false);
    const aboutMe = ref(false);
    const myCertificates = ref(false);
    const htmlCss = ref(false);
    const javaScript = ref(false);
    const python = ref(false);
    const others = ref(false);
    const myApplications = ref(false);
    const download = ref(false);
    const mySkills = ref(false);

    const openNavigation = (txt) => {
        if(txt === 'navigation') {
           navigation.value = true;
           developer.value = false;
           aboutMe.value = false;
           myCertificates.value = false;
           htmlCss.value = false;
           javaScript.value = false;
           python.value = false;
           others.value = false;
           myApplications.value = false;
           mySkills.value = false;
        } else if(txt === 'closeNavigation') {
            navigation.value = false;
            developer.value = true;
        } else if(txt === 'aboutMe') {
            aboutMe.value = true;
            navigation.value = false;
        } else if(txt === 'backAboutMe') {
            aboutMe.value = false;
            navigation.value = true;
        } else if(txt === 'closeAboutMe') {
            aboutMe.value = false;
            developer.value = true;
        } else if(txt === 'myCertificates') {
            myCertificates.value = true;
            navigation.value = false;
        } else if(txt === 'backMyCertificates') {
            myCertificates.value = false;
            navigation.value = true;
        } else if(txt === 'closeMyCertificates') {
            myCertificates.value = false;
            developer.value = true;
        } else if(txt === 'htmlCss') {
            myCertificates.value = false;
            htmlCss.value = true;
        } else if(txt === 'backHtmlCss') {
            htmlCss.value = false;
            myCertificates.value = true;
        } else if(txt === 'closeHtmlCss') {
            htmlCss.value = false;
            developer.value = true;
        } else if(txt === 'javaScript') {
            myCertificates.value = false;
            javaScript.value = true;
        } else if(txt === 'backJavaScript') {
            javaScript.value = false;
            myCertificates.value = true;
        } else if(txt === 'closeJavaScript') {
            javaScript.value = false;
            developer.value = true;
        } else if(txt === 'python') {
            myCertificates.value = false;
            python.value = true;
        } else if(txt === 'backPython') {
            python.value = false;
            myCertificates.value = true;
        } else if(txt === 'closePython') {
            python.value = false;
            developer.value = true;
        } else if(txt === 'others') {
            myCertificates.value = false;
            others.value = true;
        } else if(txt === 'backOthers') {
            others.value = false;
            myCertificates.value = true;
        } else if(txt === 'closeOthers') {
            others.value = false;
            developer.value = true;
        } else if(txt === 'myApplications') {
            myApplications.value = true;
            navigation.value = false;
        } else if(txt === 'backMyApplications') {
            myApplications.value = false;
            navigation.value = true;
        } else if(txt === 'closeMyApplications') {
            myApplications.value = false;
            developer.value = true;
        } else if(txt === 'download') {
            download.value = true;
        } else if(txt === 'closeDownload') {
            download.value = false;
        } else if(txt === 'mySkills') {
            mySkills.value = true;
            navigation.value = false;
        } else if(txt === 'backMySkills') {
            mySkills.value = false;
            navigation.value = true;
        } else if(txt === 'closeMySkills') {
            mySkills.value = false;
            developer.value = true;
        };
    };
</script>

<style scoped>
    .headWindow {
        width: 100%;
        height: 100vh;
    }
</style>
