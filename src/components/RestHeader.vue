<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>place your order before <i>they</i> show up</p>
    <div class="progbar">
      <div class="progbarfill" :style="cssVars"><p>{{items}}/10 items</p></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'RestHeader',
  props: {
    msg: String
  },
  data(){
    return{
      items: 1
    }
  },
  computed: {
    cssVars() {
      return {
        '--width': (this.items*10) + '%'
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>


ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.progbarfill>p{
  padding-left: 8px;
  margin-bottom: 4px;
  white-space: nowrap;
}

.progbar{
  display: flex;
  border-top: 1px solid rgba(0, 0, 0, 0.251);
  background-color: white;
  width: 100%;
  height: 25px;  
}
.progbarfill{
  width: var(--width);
  background-color: red;
}

</style>
