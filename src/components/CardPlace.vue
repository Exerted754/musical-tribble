<script setup>
import Card from "./Card.vue";
</script>
<template>
<div>
    <Card image="/src/cardpngs/card1.png" text="Зеленая миля (1999)" class="card-style"/>
    <Card image="src/cardpngs/card2.png" text="Список Шиндлера (1993)"  class="card-style"/>
    <Card image="src/cardpngs/card3.png" text="Побег из Шоушенка (1994)"  class="card-style"/>
    <Card image="src/cardpngs/card4.png" text="Форрест Гамп (1994)"  class="card-style"/>
    <Card image="src/cardpngs/card5.png" text="Властелин колец: Возвращение короля (2003)"  class="card-style"/>
    <Card image="src/cardpngs/card6.png" text="Властелин колец: Братство Кольца (2001)"  class="card-style"/>
    <Card image="src/cardpngs/card7.png" text="Властелин колец: Две крепости (2002)" class="card-style"/>
    <Card image="src/cardpngs/card8.png" text="1+1 (2011)"  class="card-style"/>
    <Card image="src/cardpngs/card9.png" text="Интерстеллар (2014)"  class="card-style"/>
    <Card image="src/cardpngs/card10.png" text="Тайна Коко (2017)"  class="card-style"/>
</div>
</template>

<style scoped>
div{
    display: flex;
    gap: 20px;
    overflow: hidden;
    flex-wrap: wrap;
    justify-content: center;
}

.card-style{
    max-width: 184px;
}


</style>