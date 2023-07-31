<template>
  <v-app>
    <v-app-bar style="background-color: rgb(131, 126, 126);">
      <v-container class="d-flex align-center ">
        <v-app-bar-title class="font">pomodoro</v-app-bar-title>
        <v-btn prepend-icon="mdi-cannabis" to="/" class="font">Main</v-btn>
        <v-btn prepend-icon="mdi-playlist-plus" to="/list" class="font">List</v-btn>
        <v-btn prepend-icon="mdi-music-circle-outline" to="/settings" class="font">music</v-btn>
      </v-container>
    </v-app-bar>
    <v-main style="background-color: azure;">
      <!-- Component 是目前頁面該顯示的元件 -->
      <router-view v-slot="{ Component }">
        <!-- keep-alive 讓路由切換時不會銷毀元件，用 include 指定只有 Home 不會被銷毀 -->
        <!-- component 動態元件，顯示 is 綁定的元件 -->
        <keep-alive include="Home">
          <component :is="Component"></component>
        </keep-alive>
      </router-view>
      <img src="../src/assets/cat.png" style="width: 20vw; position: fixed; bottom:0px; right: 50px; ">
    </v-main>
  </v-app>
</template>

<script setup>
</script>
<style scoped>
.font{
  color: #fff;
  font-weight: bolder;
  font-family:Arial, Helvetica, sans-serif;
}
</style>
