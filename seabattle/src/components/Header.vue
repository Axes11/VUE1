<script setup lang="ts">
  import DesignShip1 from "@/components/icons/DesignShip1.vue";
  import DesignShip2 from "@/components/icons/DesignShip2.vue";
  import Logo from "@/components/icons/Logo.vue";
</script>

<template>
  <div class="w-full flex justify-center">
    <div class="flex gap-5">
      <DesignShip1 class="ship"/>
      <Logo class="logo"/>
      <DesignShip2 class="ship"/>
    </div>
  </div>
</template>

<style scoped>
  .ship{
    width: 50px;
    height: 40px;
  }
  .logo{
    width: 160px;
    height: 40px;
  }
</style>