<script setup>
import { ref } from 'vue';

const props = defineProps({
    registration: Function,
    showLogin: Function,
    showRegistration: Function
})


</script>

<template>
    <div class="all">
        <div class="main-header">
            <div style="display: flex; flex-direction: row; gap: 18px; align-items: center;">
            <img src="../assets/logo.png" alt="logo">
            <p  class="hide_p2" style="font-size: 18px; width: 155px; ">Сайт с обзорами фильмов</p>
            </div>
            <div class="button-width">
                <button class="style-button" @click="props.showRegistration(); props.registration()">Регистрация</button>
                <button class="style-button" @click="props.showLogin(); props.registration()">Вход</button>
            </div>
        </div>
        <div style="width: 100%; height: 1px; background-color: #FFFFFF1A;"></div>
    </div>
</template>

<style scoped>
.main-header{
    display: flex;
    justify-content: space-between;
    
}
.style-button{
    border: none;
    background-color: transparent;
    cursor: pointer;    
    outline: none;
    color: #ECECEC;
    font-size: 16px;
}
.button-width{
    display: flex;
    justify-content: center;
}
.all{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}
</style>