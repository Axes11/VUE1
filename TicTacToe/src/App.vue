<script setup>
import { nextTick, ref } from "vue";
import { RouterLink, RouterView } from "vue-router";

let cells = ref([null, null, null, null, null, null, null, null, null]);

let whoPickingNow = 0;
let gameSituation = "Game isnt started";

function checkWhoWon() {
  const combinationsToWin = [
    [0, 1, 2], // Первая линия
    [3, 4, 5], // Вторая линия
    [6, 7, 8], // Третья линия
    [0, 3, 6], // Первый столбец
    [1, 4, 7], // Второй столбец
    [2, 5, 8], // Третий столбец
    [0, 4, 8], // Диагональ
    [2, 4, 6], // Диагональ
  ];

  for (let combination of combinationsToWin) {
    const [a, b, c] = combination;
    if (
      cells.value[a] !== null &&
      cells.value[a] === cells.value[b] &&
      cells.value[a] === cells.value[c]
    ) {
      gameSituation = cells.value[a] === 0 ? "0 Wins!" : "1 Wins!";
      return;
    }
  }

  if (!cells.value.includes(null)) {
    gameSituation = "Draw!";
  }
}

function changeCellToCircle(cellIndex) {
  if (cells.value[cellIndex] === null) {
    cells.value[cellIndex] = whoPickingNow;
    whoPickingNow = 1 - whoPickingNow;
    checkWhoWon();
  }
}

function changeBg(cellIndex) {
  const value = cells.value[cellIndex];
  if (value === 0) {
    return "circle";
  } else if (value === 1) {
    return "cross";
  } else {
    return "";
  }
}
</script>

<template>
  <div class="background">
    <div class="flex flex-wrap wrapper">
      <div
        v-for="(cell, index) in cells"
        @click="changeCellToCircle(index)"
        :key="index"
        class="cell"
        :class="changeBg(index)"
      ></div>
    </div>
  </div>

  <div class="navigation flex justify-center items-center">
    <span class="text-4xl">{{ gameSituation }}</span>
  </div>
</template>

<style scoped>
.background {
  background-color: rgb(19, 19, 19);
}

.wrapper {
  max-width: 450px;
}

.cross {
  background-image: url("./assets/img/cross.png");
  background-size: contain;
  background-repeat: no-repeat;
}

.circle {
  background-image: url("./assets/img/circle.png");
  background-size: contain;
  background-repeat: no-repeat;
}

.cell {
  width: 150px;
  height: 150px;
  background-color: rgb(37, 37, 37);
  border: 1px solid white;
}
</style>
