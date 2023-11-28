<template>

  <div class="menu">
    <a v-for="(menuName, i) in mainMenus" :key="i">no.{{i}} {{menuName}}</a>
  </div>

  <div v-for="(product, i) in products" :key="i">
    <h4>{{product.roomName}} 원룸</h4>
    <p>{{product.price}} 만원</p>
    <button @click="declaration(i)">허위매물신고</button> <span>신고수 : {{ product.declarations }}</span>
  </div>

</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      mainMenus: ['Home', 'Shop', 'About'],
      products: [
        {roomName: '전대리원룸', price: 65, declarations: 0},
        {roomName: '둔전원룸', price: 60, declarations: 0},
        {roomName: '유방동원룸', price: 75, declarations: 0}
      ],
    }
  },
  methods: {
    declaration: function(id) {
      this.products[id].declarations += 1;
      // return
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
  margin-top: 5px;
}

.menu {
  background: darkslateblue;
  padding: 10px;
  border-radius: 5px;
}
.menu a {
  height: 40px;
  line-height: 40px;
  font-size: 25px;
  color: white;
  padding: 25px;
}
</style>
