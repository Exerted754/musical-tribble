<script setup>
import { ref } from 'vue';


const props = defineProps({
    activeForm: {
        type: String,
        default: 'registration',
    },
    showLogin: Function,
    showRegistration: Function,
    registration: Function,
})

const formData = ref({
    name: '',
    email: '',
    phone: '',
    password: '',
    password_sub: '',
})

function submit() {
    console.log(Object.values(formData.value))
}
</script>
<template>
    <div class="background-form">
        <form class="form" >
            <img @click="registration" src="../assets/close.png" alt="close" style="position: absolute; top: 20px; right: 20px;">
            <legend style="display: flex; flex-direction: row; justify-content: center; gap: 30px;">
                <button type="button" @click="props.showRegistration()" :class="{'active-button': props.activeForm === 'registration', 'inactive-button': props.activeForm !== 'registration'}" class="button-reg-log">Регистрация</button>
                <button type="button" @click="props.showLogin()" :class="{'active-button': props.activeForm === 'login', 'inactive-button': props.activeForm !== 'login'}" class="button-reg-log">Авторизация</button>
            </legend>
            <div v-show="props.activeForm == 'registration'" class="form-content">
                <div class="allinput">
                    <input type="text" v-model="formData.name" required minlength="3" placeholder="Ваше имя" name="name" style="width: 480px">
                    <input type="email" v-model="formData.email" required placeholder="Email" name="email" autocomplete="email">
                    <input type="tel" v-model="formData.phone" required placeholder="+7 (___) ___-__-__" name="phone" autocomplete="tel"/>
                    <input type="password" v-model="formData.password" required minlength="8" name="password" placeholder="Пароль">
                    <input type="password" v-model="formData.password_sub" required minlength="8" name="password_sub" placeholder="Повторите пароль">
                </div>
                <div>
                    <div class="checker">
                        <input required type="checkbox" class="checkmarker">
                        <span style="color: #181818;">Согласен на обработку <a style="color: #FF9C07">персональный данных</a></span>
                    </div>
                    <button type="submit" class="reg-button" style="margin-top: 20px;">Зарегистрироваться</button> 
                </div>
                <div class="info-style">
                    <img src="../assets/info.png" alt="info">
                    <div style="color: #838383; display: flex; justify-content: center;">Все поля обязательны для заполнения</div>
                </div>
            </div>

            <div v-show="props.activeForm == 'login'" class="form-content">
                <div class="allinput">
                    <input required type="email" placeholder="Email">
                    <input required type="password" placeholder="Пароль">
                </div>
                <button type="submit" class="reg-button">Войти</button> 
                <div class="info-style">
                    <img src="../assets/info.png" alt="info">
                    <div style="color: #838383; display: flex; justify-content: center;">Все поля обязательны для заполнения</div>
                </div>
            </div>
        </form>
    </div>
</template>
<style scoped>
.background-form{
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background: rgba(0, 0, 0, 0.5);
  backdrop-filter: blur(10px); 
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000; 
  overflow: hidden; 
}

.form{
    width: 600px; 
    background-color: white;
    justify-content: center;
    position: relative;
    display: flex;
    flex-wrap: wrap;
    border-radius: 20px;
    padding: 40px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    z-index: 1001;
    position: relative;
    transform: scale(0.9);
    animation: showForm 0.3s forwards ease-out;
}
@keyframes showForm {
  from {
    opacity: 0;
    transform: scale(0.9);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}

.info-style{
    display: flex;
    justify-content: center;
    gap: 12px;
}
.form-content{
    margin-top: 30px;
    display: flex;
    flex-direction: column;
    gap: 30px;
}
.checker{
    display: flex;
    justify-content: center;
    gap: 12px;
    align-items: center;
}
.checkmarker{
    width: 20px;
    height: 20px;
    cursor: pointer;
}
.allinput{
    width: 520px;
    display: flex;
    gap: 20px;
    flex-wrap: wrap;
}
input{
    width: 206px;
    padding: 20px;
    border-radius: 10px;
    border-color: #B9B9B9;
    color: #181818;
}
legend{
    width: 73.8%;
    align-items: center;
    display: flex;
    justify-content: space-between;
}
.button-reg-log{
    font-family: Inter;
    font-size: 32px;
    text-align: left;
    background-color: transparent;
    outline: none;
    border: none;
}
.active-button{
    color: #181818;
}
.inactive-button{
    color: #B9B9B9;
}

.reg-button{
    background-color: #FF9C07;
    width: 520px;
    padding: 20px;
    border-radius: 10px;
    border: none;
    outline: none;
}


.checkmarker {
  appearance: none;
  -webkit-appearance: none;
  width: 20px;
  height: 20px;
  background-color: #f0f0f0;
  border: 2px solid #ccc;
  border-radius: 4px;
  cursor: pointer;
  padding: 0; 
  margin: 0; 
  box-sizing: border-box;
}

.checkmarker:checked {
  background-color: #FF9C07;
  border-color: #FF9C07;
}

.checkmarker:checked::before {
  content: "✔";
  color: white;
  display: block;
  text-align: center;
  font-size: 16px;
  line-height: 20px;
}
</style>