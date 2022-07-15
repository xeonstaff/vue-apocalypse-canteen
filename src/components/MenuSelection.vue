<!-- drag-and-drop from the Tyler Potts Youtube tutorial -->

<template>
  <div
    :food-id="food.id"
    @dragover.prevent
    @drop.prevent="drop"
  >
    <slot />
  </div>
</template>

<script>
export default {
  props: ['foodId'],
  methods: {
    drop: e=>{
      const foodId = e.dataTransfer.getData('foodId')
      const card = document.getElementById(foodId)
      card.style.display = "block"
      e.target.appendChild(card)
    }
  },
}
</script>

<style scoped>
h1{
    font-size: 100px;
}


</style>
