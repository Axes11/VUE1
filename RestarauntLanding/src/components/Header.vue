<script setup lang="ts">

</script>

<template>
  <div class="flex justify-between items-center">
    <div class="header_logo flex flex-col items-center gap-2">
      <img class="header_logo__img" src="./icons/logo.png" alt="logo">
      <span class="nycd">Restaraunt</span>
    </div>
    <ul class="flex gap-3 montserrat font-light text">
      <li>Menu</li>
      <li>Tables</li>
      <li>Reviews</li>
      <li>Contacts</li>
    </ul>
    <span class="montserrat font-extralight undertitle">+ 48 834 438 388</span>
  </div>
</template>

<style scoped>
  .header_logo__img{
    width: 60px;
  }
</style>