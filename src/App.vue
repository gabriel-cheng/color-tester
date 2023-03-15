<script setup lang="ts">
import { ref } from 'vue';
const inputColor = ref("");

function setColor() {
  const colorBox = document.querySelector(".c-box-colorfull") as HTMLDivElement;

  colorBox.style.backgroundColor = inputColor.value;
}
</script>

<template>
  <div style="margin: 0 10px;">
    <header>
      <div class="h-items">
        <div class="h-icon-container">
          <img src="/favicon.png" alt="" class="">
        </div>
        <div class="h-txt-container">
          <p>color tester</p>
          <div class="by">
            <p style="font-size: 1.5rem; text-transform: initial;">By: Gabriel Carvalho</p>
          </div>
        </div>
      </div>
    </header>

    <main class="m-container">
      <div class="m-subcontainer">
        <div class="c-container">
          <div class="t-container">
            <h1>Informe o código ou nome da cor</h1>
          </div>
          <div class="i-container">
            <input @input="setColor();" v-model="inputColor" type="text" placeholder="Ex: #a1a1a1">
          </div>
        </div>
        <div class="c-box-container">
          <p>*A cor abaixo irá se alterar assim que for reconhecida*</p>
          <div class="c-box-colorfull">
            <p>{{ inputColor }}</p>
          </div>
        </div>
      </div>
    </main>
  </div>
</template>

<style scoped>
header {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 30px 0;
  width: 100%;
}
.h-icon-container {
  margin: 0 20px 0 0;
}
.h-items {
  display: flex;
  align-items: center;
}
.h-icon-container img {
  max-width: 80px;
  width: 100%;
}
.h-txt-container p {
  color: #fff;
  font-size: 4rem;
  text-transform: uppercase;
}
.by {
  width: 100%;
  text-align: end;
}
.m-container {
  width: 100%;
  height: calc(100vh - 145px);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.m-subcontainer {
  max-width: 680px;
  width: 100%;
}
.c-box-container {
  margin: 50px 0 0 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  font-size: 2rem;
  color: #fff;
}
.c-box-container p {
  margin: 0 0 10px 0;
  text-align: center;
}
.c-box-colorfull {
  background-color: #a1a1a1;
  width: 100%;
  height: 300px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 4rem;
}
.c-box-colorfull p {
  text-shadow: 2px 1px black;
}
.t-container {
  margin: 0 0 20px 0;
  text-align: center;
}
.t-container h1 {
  color: #fff;
  text-transform: uppercase;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 3rem;
}
.i-container {
  display: flex;
  justify-content: center;
}
.i-container input {
  max-width: 300px;
  width: 100%;
  outline: 0;
  border: 0;
  height: 40px;
  font-size: 3rem;
  padding: 0 10px;
}
@media screen and (max-width: 597px) {
  .t-container h1 {
    font-size: 4.5vw;
  }
}
@media screen and (max-width: 461px) {
  .c-box-container p {
    text-align: center;
  }
}
@media screen and (max-width: 412px) {
  .h-txt-container p {
    font-size: 9vw;
  }
}
@media screen and (max-width: 349px) {
  .h-txt-container p {
    font-size: 8vw;
  }
}
</style>
