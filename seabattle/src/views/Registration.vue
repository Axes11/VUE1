<script setup lang="ts">
  import DesignShip1 from "@/components/icons/DesignShip1.vue";
  import DesignShip2 from "@/components/icons/DesignShip2.vue";
  import Header from "@/components/Header.vue";
</script>

<template>
  <Header/>
  <div class="h-screen flex items-center justify-center">
    <div class="wrapper flex justify-between p-8">
      <div class="registration flex flex-col items-center justify-between gap-5">
        <DesignShip1 class="ship"/>
        <div class="flex flex-col gap-3">
          <input class="input" placeholder="NAME..." type="text" name="name" id="reg__name">
          <input class="input" placeholder="E-MAIL..." type="text" name="email" id="reg__email">
          <input class="input" placeholder="PASSWORD..." type="text" name="password" id="reg__pass">
        </div>
        <button class="button w-full">REGISTER</button>
      </div>
      <div class="login flex flex-col items-center justify-between">
        <DesignShip2 class="ship"/>
        <div class="flex flex-col gap-3">
          <input class="input" placeholder="NAME..." type="text" name="name" id="log_name">
          <input class="input" placeholder="PASSWORD..." type="text" name="pass" id="log__pass">
        </div>
        <button class="button w-full">LOGIN</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
  .wrapper {
    background-image: url("/RegBg.png");
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    border-radius: 30px;
    width: auto;
    height: auto;
    gap: 50px;
  }
  .ship{
    width: 120px;
    height: 100px;
  }
</style>
