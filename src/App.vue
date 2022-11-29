<template>
  <div class="black-bg" v-if="isModalOpen == true">
    <div class="white-bg">
      <h4>detail</h4>
      <p>detail</p>
      <button @click="isModalOpen = false">close</button>
    </div>
  </div>
  <div class="menu">
    <a v-for="menu in menus" :key="menu">
      {{ menu }}
    </a>
  </div>
  <div v-for="room, i in rooms" :key="i">
    <img :src="room.image" class="room-img">
    <h4>{{ room.title }}</h4>
    <p>{{ room.price }}원</p>
  </div>
</template>

<script>
import roomdata from './assets/room';
export default {
  name: 'App',
  data() {
    return {
      menus: ['Home', 'Shop', 'About'],
      rooms: roomdata,
    }
  },
  methods: {
    increase(i) {
      this.numberOfReports[i]++
    },
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
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}

.room-img {
  width: 100%;
  margin-top: 40px;
}

body {
  margin: 0;
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}

.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>
