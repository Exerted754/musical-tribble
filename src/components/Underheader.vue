<template>
    <div style="display: flex; justify-content: space-between; gap: 90px">
        <div style="font-size:calc(26px + 1.5vw)">Топ 20 фильмов</div>
        <button>
            <img src="../assets/+.png" alt="plus">
            <p class="hide_p">Добавить обзор</p>
        </button>
    </div>
</template>

<style scoped>
div{
    display: flex;
    justify-content: space-between;
    align-items: center;
}
h1{
    font-size: 48px;
    width: 80%;
}
button{
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #FF9C07;
    outline: none;
    padding: 20px;
    border: none;
    width: 199px;
    height: 60px;
    border-radius: 10px;
    font-family: 'Inter';
    font-size: 16px;
    font-weight: 600;
    line-height: 20px;
    color: #ECECEC;
}
</style>