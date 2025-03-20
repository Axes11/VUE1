<template>
  <div class="area">
    <div v-for="cell in 64" :key="cell" class="area__cell"></div>
  </div>
</template>

<style scoped>
.area {
  display: grid;
  grid-template-columns: repeat(8, 1fr);
  grid-template-rows: repeat(8, 1fr);
  gap: 1px;
}

.area__cell {
  min-width: 50px;
  min-height: 50px;

  width: 100%;
  height: 100%;
  background-color: #035BFF;
  transition: background-color 0.3s;
}

.area__cell:hover {
  background-color: #2c77ff;
  cursor: pointer;
}
</style>
