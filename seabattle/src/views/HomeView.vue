<script setup lang="ts">
  import DesignShip1 from "@/components/icons/DesignShip1.vue";
  import DesignShip2 from "@/components/icons/DesignShip2.vue";
  import Logo from "@/components/icons/Logo.vue";

  const redirectToRegistration = (isAlreadyLoggined : boolean) => {
    if(isAlreadyLoggined){
      window.location.href = "/game"
    }else{
      window.location.href = "/registration"
    }
  }
</script>

<template>
  <div class="wrapper h-screen flex items-center justify-center">
    <div class="flex items-center flex-col text-center">
      <div class="flex items-center gap-5">
        <DesignShip1 class="ship"/>
        <Logo class="logo"/>
        <DesignShip2 class="ship"/>
      </div>
      <button class="button mt-5" @click="redirectToRegistration(false)">START GAME</button>
    </div>
  </div>
</template>

<style scoped>
  .ship{
    width: 180px;
    height: 150px;
  }
  .logo{
    width: 500px;
    height: 120px;
  }
</style>
