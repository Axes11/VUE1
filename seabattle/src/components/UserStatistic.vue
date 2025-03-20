<script setup lang="ts">
    const props = defineProps(['name', 'games', 'wins', 'lose', 'surrenders', 'avatarSrc']);
</script>

<template>
  <div class="flex items-center flex-col">
    <div class="flex items-center flex-col gap-5">
      <div class="avatar">
        <img :src=avatarSrc alt="Avatar">
      </div>
      <p class="text-2xl white">{{ name }}</p>
    </div>
    <div class="flex flex-col gap-5">
      <div class="decor__line"></div>
      <p class="text-xl white">Games : {{ games }}</p>
      <p class="text-xl white">Wins : {{ wins }}</p>
      <p class="text-xl white">Lose : {{ lose }}</p>
      <p class="text-xl white">Surrenders : {{ surrenders }}</p>
    </div>
  </div>
</template>

<style scoped>
  .avatar {
    width: auto;
    height: auto;

    min-width: 50px;
    min-height: 50px;

    max-width: 150px;
    max-height: 150px;

    border-radius: 50%;
    border: 3px solid #252525;

    object-fit: cover;
  }
  .decor__line{
    width: 100%;
    height: 3px;
    background-color: #D85B02;
  }
</style>