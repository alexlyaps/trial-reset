<script setup>
import { ref } from 'vue';
import Screen1 from './components/Screen1.vue';
import Screen2 from './components/Screen2.vue';
import Screen3 from './components/Screen3.vue';

const currentScreen = ref(null); 
const showScreen = (screenNumber) => {
  currentScreen.value = screenNumber; 
};
</script>

<template>
  <div>
    <div class="buttons" v-if="currentScreen === null">
      <button @click="showScreen(1)">Screen 1</button>
      <button @click="showScreen(2)">Screen 2</button>
      <button @click="showScreen(3)">Screen 3</button>
    </div>
    <div class="screens" v-else>
      <Screen1 v-if="currentScreen === 1" />
      <Screen2 v-else-if="currentScreen === 2" />
      <Screen3 v-else-if="currentScreen === 3" />
    </div>
  </div>
</template>

<style scoped lang="scss">
@import "@/styles/variables.scss";

div.buttons {
  display: flex;
  margin: auto;
  justify-content: space-between;
  gap: 20px;

  button {
    border-radius: 8px;
    height: 44px;
    width: 80px;
    border: 1px #6F6BFC solid;
    background-color: $button-one-color;
    color: $button-one-text-color;
    transition: all 0.3s ease;
    &:hover {
      background-color: $button-one-color-hover;
    }
    &:active {
      background-color: $button-one-color;
      box-shadow: 0 0 0 4px #F4EBFF;        
    }
    &:disabled {
      background-color: $button-one-color-disabled;
      border: 1px $button-one-color-disabled solid;        
    }
  }}
</style>
