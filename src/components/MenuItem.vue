<template>
  <div
    :foodId="foodId"
    class="card"
    draggable=true
    @dragstart="dragStart"
    @dragover.stop
    >
    <div class="foodgroup">
      <img 
        :src="foodImage" 
        :alt="foodName" 
        draggable=false
        />
        <h5 class="foodtile"> {{foodName}} </h5>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MenuItem',
  props: {
    foodName: String,
    foodImage: String,
    foodId: Number
  },
  methods: {
    dragStart: e=>{
      const target = e.target;
      e.dataTransfer.setData('foodId', target.foodId)
      setTimeout(()=>{
        target.style.display = "none"
      }, 0)
    }
  }
}
</script>

<style scoped>
  img{
    width: 100px;
    height: 60px;
  }

  h5{
    word-wrap: break-word;
  }

  .panel-heading{
    display: flex;
    justify-content: center;
  }

  .foodtitle{
    border: 1px solid rgba(0, 0, 0, 0.3);
    background: #5b5d8e5c;
  }

  .foodgroup{
    display: flex;
    flex-direction: column;
    justify-content: center;
    border: 1px solid rgba(0, 0, 0, 0.2);
    border-radius: 5px;
    margin: 5px;
    padding: 5px;
    max-width: 120px;
  }

</style>
