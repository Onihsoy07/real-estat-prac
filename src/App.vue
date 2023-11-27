<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div>
    <h4>{{rooms[0]}} 원룸</h4>
    <p>{{price[0]}} 만원</p>
  </div>
  <div>
    <h4>{{rooms[1]}} 원룸</h4>
    <p>{{price[1]}} 만원</p>
  </div>
  <div>
    <h4>{{rooms[2]}} 원룸</h4>
    <p>{{price[2]}} 만원</p>
  </div>

</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      price : [65, 60, 75],
      rooms : ['전대리원룸', "둔전원룸", "유방동원룸"],
      
    }
  },
  components: {
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
