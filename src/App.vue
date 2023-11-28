<template>

  <div class="black-bg" v-if="isModalOpen">
    <div class="white-bg">
      <div class="modal-close-btn" @click="modalClose()">X</div>
      <h4>{{ modalTitle }}</h4>
      <h4>{{ modalDetail }}</h4>
    </div>
  </div>

  <div class="menu">
    <a v-for="(menuName, i) in mainMenus" :key="i">no.{{i}} {{menuName}}</a>
  </div>

  <div v-for="(product, i) in products" :key="i">
    <img :src="require(`${product.imageSrc}`)" class="room-img">
    <h4 @click="modalOpen(i)">{{product.roomName}} 원룸</h4>
    <p>{{product.price}} 만원</p>
    <button @click="declaration(i)">허위매물신고</button> <span>신고수 : {{ product.declarations }}</span>
  </div>

</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      isModalOpen: false,
      modalTitle: '',
      modalDetail: '',
      mainMenus: ['Home', 'Shop', 'About'],
      products: [
        {roomName: '전대리원룸', price: 65,
         declarations: 0, imageSrc: './assets/room0.jpg',
         detail: '전대리원룸은  ~~~'},
        {roomName: '둔전원룸', price: 60,
         declarations: 0, imageSrc: './assets/room1.jpg',
         detail: '둔전원룸은  ~~~'},
        {roomName: '유방동원룸', price: 75,
         declarations: 0, imageSrc: './assets/room2.jpg',
         detail: '유방동원룸은  ~~~'},
      ],
    }
  },
  methods: {
    declaration: function(id) {
      this.products[id].declarations += 1;
      // return
    },
    modalOpen: function(id) {
      this.modalTitle = this.products[id].roomName;
      this.modalDetail = this.products[id].detail;
      this.isModalOpen = true;
    },
    modalClose: function() {
      this.isModalOpen = false;
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
.room-img {
  width: 70%;
  height: auto;
  margin-top: 40px;
}
body{
  margin: 0;
  padding: 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed;
  top: 0;
  padding: 20px;
}
.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
.modal-close-btn {
  float: right;
  cursor: pointer;
}
</style>
