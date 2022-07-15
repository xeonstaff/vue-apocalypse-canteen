<template>
  <div class="menuboard">
    <div v-for="food in menu_items" :key="food.name">
      <app-menu-item 
        :food-name="food.name" 
        :food-image="food.img"
        :food-id="food.id">
      </app-menu-item>
    </div>
  </div>
</template>

<script>
import menu_items from '../assets/menu_items.js'
import MenuItem from './MenuItem.vue'

export default {
  // name: 'MenuBoard',
  data() {
    return{
      menu_items,
    } 
  },
  components: {
    appMenuItem: MenuItem
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.menuboard{
  display: flex;
  flex-wrap: wrap;
  max-width: 35vw;
}


</style>
