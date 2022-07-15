<template>
  <div id="app">
    <div class="restbox">
      <RestHeader msg="Welcome to the Drumlin Diner"/>
    </div>
    <div class="flex-container">
      <div class="restbox flex-child">
        <MenuBoard />
      </div>
      <div class="restbox flex-child">
        <app-menu-selection ></app-menu-selection >
      </div>
    </div>
  </div>
</template>

<script>
import RestHeader from './components/RestHeader.vue'
import MenuBoard from './components/MenuBoard.vue'
import MenuSelection from './components/MenuSelection.vue'

export default {
  name: 'App',
  components: {
    RestHeader,
    MenuBoard,
    appMenuSelection:MenuSelection
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;1,400;1,700&display=swap');

*{
  margin: 0px;
  padding: 0px;
}

p, h1, h5{
  font-family: 'Space Mono', 'san-serif'
}

.restbox{
  margin-top: 8vh;
  margin-left: 4vw;
  width: fit-content;
  background-color: rgba(255, 255, 255, 0.634);
  padding: 5px 15px 5px 15px;
  border: 1px rgba(0, 0, 0, 0.088) solid;
  border-left: 5px solid rgba(28, 28, 96, 0.711);
  box-shadow: 3px 3px rgba(0, 0, 0, 0.195);
}

.flex-container{
  display: flex
}

.flex-child{
  flex: 1
}

body{
  background-image: url("./assets/diner_background.png");
  background-repeat: no-repeat;
  background-size:cover;  

}

</style>
