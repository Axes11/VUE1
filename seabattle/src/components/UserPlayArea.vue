<template>
  <div class="flex flex-col">
    <div class="area">
      <div v-for="cell in 64" :key="cell" class="area__cell"></div>
    </div>
    <div class="ships flex flex-col mt-5">
      <div class="ship__container flex items-center justify-between">
        <img class="ship ship--1" src="/1.png" alt="1 cell ship">
        <span>1 cell ship</span>
      </div>
      <div class="ship__container flex items-center justify-between">
        <img class="ship ship--2" src="/2.png" alt="2 cell ship">
        <span>2 cell ship</span>
      </div>
      <div class="ship__container flex items-center justify-between">
        <img class="ship ship--3" src="/3.png" alt="3 cell ship">
        <span>3 cell ship</span>
      </div>
      <div class="ship__container flex items-center justify-between">
        <img class="ship ship--4" src="/4.png" alt="4 cell ship">
        <span>4 cell ship</span>
      </div>
    </div>
  </div>
</template>

<style scoped>
.area {
  display: grid;
  grid-template-columns: repeat(8, 1fr);
  grid-template-rows: repeat(8, 1fr);
  gap: 1px;

  margin-bottom: 20px;
}
.ships{
  display: flex;
  flex-direction: column;
  gap: 10px;
}
.ship__container{
  border-radius: 10px;
  padding: 10px;
}
.ship__container:hover{
  transform: scale(1.1);
  background-color: rgb(62, 61, 61);
  border-radius: 10px;
  padding: 10px;
  cursor: pointer;
}
.area__cell {
  min-width: 50px;
  min-height: 50px;
  background-color: #035BFF;
  transition: background-color 0.3s;
}
.area__cell:hover {
  background-color: #2c77ff;
  cursor: pointer;
}
.ship--1{
  width: 15%;
}
.ship--2{
  width: 30%;
}
.ship--3{
  width: 45%;
}
.ship--4{
  width: 60%;
}
</style>
