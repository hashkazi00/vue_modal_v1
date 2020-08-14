<template>
  <div id="app">
    <Modal v-if="showModal" @subOne="subOne" @addOne="addOne" :num="num" />
    <div class="container">
      <button v-if="!showModal" @click="showModal = !showModal" class="viewModal">Click Me !!!</button>
      <div class="show-number">{{num}}</div>
    </div>
  </div>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  data() {
    return {
      showModal: false,
      num: 0
    };
  },
  components: {
    Modal
  },
  methods: {
    addOne() {
      this.num++;
      this.showModal = false;
    },
    subOne() {
      this.num--;
      this.showModal = false;
    }
  }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Poppins:400,600,700&display=swap");
*,
*::after,
*::before {
  margin: 0;
  padding: 0;
  -webkit-box-sizing: inherit;
  box-sizing: inherit;
}

html {
  font-size: 62.5%;
}
body {
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  font-family: "Poppins", sans-serif;
  position: relative;
  height: 100vh;
}
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding-top: 25%;
  transform: translateY(-25%);
  text-align: center;
}

.viewModal {
  border: none;
  cursor: pointer;
  background: none;
  font-size: 1.6rem;
  color: rgb(0, 0, 0);
  padding: 8px 20px;
  /* margin-right: 20px; */
  outline: none;
  border: 1px solid grey;
  border-radius: 100px;
}

.show-number {
  margin-top: 2.5rem;
  font-size: 4rem;
}
</style>
