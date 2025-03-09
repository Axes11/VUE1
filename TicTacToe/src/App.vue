<script setup>
import { ref } from "vue";

const cells = ref(Array(9).fill(null));
const whoPickingNow = ref(1);
const gameSituation = ref("Game isn't started");

const combinationsToWin = [
  [0, 1, 2], [3, 4, 5], [6, 7, 8],
  [0, 3, 6], [1, 4, 7], [2, 5, 8],
  [0, 4, 8], [2, 4, 6],
];

function checkWhoWon() {
  for (let [a, b, c] of combinationsToWin) {
    if (cells.value[a] !== null && cells.value[a] === cells.value[b] && cells.value[a] === cells.value[c]) {
      gameSituation.value = cells.value[a] === 1 ? "Cross Wins!" : "Circle Wins!";
      return;
    }
  }
  if (!cells.value.includes(null)) {
    gameSituation.value = "Draw!";
  }
}

function handleCellClick(cellIndex) {
  if (cells.value[cellIndex] === null && !gameSituation.value.includes("Wins")) {
    cells.value[cellIndex] = whoPickingNow.value;
    whoPickingNow.value = 1 - whoPickingNow.value; // Переключение хода
    checkWhoWon();
  }
}

function getCellClass(cellIndex) {
  return cells.value[cellIndex] === 1
    ? "cross"
    : cells.value[cellIndex] === 0
    ? "circle"
    : "";
}

function resetGame() {
  cells.value = Array(9).fill(null);
  whoPickingNow.value = 1;
  gameSituation.value = "Game isn't started";
}
</script>

<template>
  <div class="background">
    <div class="flex flex-wrap wrapper">
      <div
        v-for="(cell, index) in cells"
        :key="index"
        class="cell"
        :class="getCellClass(index)"
        @click="handleCellClick(index)"
      ></div>
    </div>

    <div class="status flex justify-center items-center">
      <span class="text-2xl font-semibold">{{ gameSituation }}</span>
    </div>

    <div class="controls flex justify-center items-center mt-4">
      <button @click="resetGame" class="reset-button">Restart Game</button>
    </div>
  </div>
</template>

<style scoped>
.background {
  background-color: #131313;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  color: white;
  font-family: Arial, sans-serif;
}

.wrapper {
  display: grid;
  grid-template-columns: repeat(3, 150px);
  gap: 5px;
}

.cell {
  width: 150px;
  height: 150px;
  background-color: #252525;
  border: 1px solid #fff;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: transform 0.2s ease;
}

.cell:hover {
  transform: scale(1.05);
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

.status {
  margin-top: 20px;
}

.reset-button {
  background-color: #ff5722;
  color: white;
  border: none;
  padding: 10px 20px;
  font-size: 16px;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.reset-button:hover {
  background-color: #e64a19;
}
</style>
