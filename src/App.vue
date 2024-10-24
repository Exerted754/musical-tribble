<script setup>
import Header from "./components/Header.vue";
import Underheader from "./components/Underheader.vue";
import CardPlace from "./components/CardPlace.vue";
import Footer from "./components/Footer.vue";
import AutoForm from "./components/AutoForm.vue";
import { ref } from "vue";


const reg = ref(false);
const activeForm = ref('registration');



const showRegistration = () => {
  activeForm.value = 'registration'
}
const showLogin = () => {
  activeForm.value = 'login'
}


function swap_registration(){
  if (reg.value)
    reg.value = false;
  else
    reg.value = true;
}
</script>

<template>

  <Header :registration="swap_registration" :showLogin="showLogin" :showRegistration='showRegistration' class="header-style"/>
  <Underheader class="under-header-style"/>
  <CardPlace class="cardplace-style"/>

  <AutoForm v-show="reg" :formData="formData" :registration="swap_registration" :activeForm="activeForm" :showLogin="showLogin" :showRegistration='showRegistration' class="autoForm-style"/>
  <button>
    <img src="./assets/arrow.png" alt="arrow">
    <p>Показать еще</p>
  </button>

  <Footer class="footer-style"/>

</template>

<style scoped>
.header-style{
  height: 75px;
}
.under-header-style{
  margin-top: 30px;
}
.cardplace-style{
  height: 972px;
  margin-top: 40px;
}
button{
  margin-top: 40px;
  width: 100%;
  height: 60px;
  padding: 20px;
  gap: 10px;
  border-radius: 10px;
  border: 2px solid #FF9C07;
  background-color: transparent;
  top: 40px;
  display: flex;
  justify-content: center;
  align-items: center;
  color: #FF9C07;
}
.footer-style{
  margin-top: 40px;
  height: 99px;
}
</style>