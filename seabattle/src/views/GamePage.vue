<script setup lang="ts">
  import Header from "@/components/Header.vue";
  import UserStatistic from "@/components/UserStatistic.vue";
  import UserPlayArea from "@/components/UserPlayArea.vue"
</script>

<template>
  <div class="flex flex-col gap-8">
    <Header class="mb-8"/>
    <div class="w-full flex flex-col items-center gap-5 justify-center">
      <div class="text-2xl white">10 : 19</div>
      <button class="button">SURRENDER</button>
    </div>
    <div class="flex items-center justify-between gap-6">
      <UserStatistic name="Axes" games="12" wins="8" lose="4" surrenders="0" />
      <UserPlayArea/>
      <div>
        <img src="" alt="">
        10 sec
        <img src="" alt="">
      </div>
      <UserPlayArea/>
      <UserStatistic name="Whitar" games="8" wins="4" lose="4" surrenders="0" />
    </div>
  </div>
</template>

<style scoped>
</style>