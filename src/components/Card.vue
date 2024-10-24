<script setup>
const props = defineProps({
    image: String,
    text: String
});
console.log(props.image);
</script>

<template>
<div class="card-style">
    <img :src="image" alt="image">
    <div class="text">   
        <div class="title">{{ text }}</div>
        <div class="date">Добавлено 15 августа</div>
    </div>
    <button>Подробнее</button>
</div>  
</template>

<style scoped>
.card-style{
    min-width: 176px;   
    height: 436px;
    background-color: #242424;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-direction: column;
    padding: 20px;
    gap: 16px;
    border-radius: 20px;
    overflow: hidden;
}
@media (max-width > 1920px) {
    .card-style{
        width: 184px;
    }
}

@media (max-width <= 720px) {
    .card-style{
        width: 176px;
    }
}
@media (max-width <= 320px) {
    .card-style{
        width: 134px;
        height: 357px;
    }
}



.card-style button{
    background-color: transparent;
    border: 2px solid #FF9C07;
    color: #FF9C07;
    border-radius: 10px;
    width: 184px;
    height: 44px;
    padding: 12px 16px 12px 16px;
    gap: 10px;
}
.title{
    font-family: Inter;
    font-size: 20px;
    font-weight: 500;
    text-align: left;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
    overflow: hidden;
    text-overflow: ellipsis;
}   
.date{
    font-family: Inter;
    font-size: 14px;
    font-weight: 400;
    text-align: left;
    color: #989898;
}
.text{
    width: 100%;
    display: flex;
    justify-content: space-between;
    flex-direction: column;
    gap: 12px;
}

img{
    border-radius: 12px;
    justify-content: center;
}
</style>