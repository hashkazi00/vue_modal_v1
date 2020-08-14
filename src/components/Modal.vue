<template>
  <transition name="modal">
    <div class="modal-mask">
      <div class="modal-wrapper">
        <div class="modal-container">
          <h2>😨 Are you sure you want to do this?</h2>
          <p>Please note your actions.</p>
          <div class="modal-buttons">
            <button @click="addOne">Add One</button>
            <button @click="subOne">Sub One</button>
          </div>
        </div>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  name: "Modal",
  props: ["num"],
  methods: {
    addOne() {
      this.$emit("addOne");
    },
    subOne() {
      this.$emit("subOne");
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.modal-mask {
  position: fixed;
  z-index: 9998;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: table;
  transition: opacity 0.3s ease;
}

.modal-wrapper {
  display: table-cell;
  vertical-align: middle;
}

.modal-container {
  width: 25%;
  margin: 0px auto;
  padding: 30px 30px;
  background-color: rgb(27, 27, 27);
  border-radius: 5px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.33);
  color: #fff;
  transition: all 0.3s ease;
  font-family: Helvetica, Arial, sans-serif;
  text-align: center;
}

.modal-container h2 {
  font-size: 2rem;
  margin-top: 0;
  color: #ffffff;
  font-weight: Bold;
  border-bottom: 1px solid rgba(255, 255, 255, 0.116);
  padding-bottom: 20px;
}

.modal-container p {
  opacity: 0.5;
  font-size: 1.8rem;
  margin-top: 20px;
  color: #ffffff;
}

.modal-buttons {
  display: flex;
  justify-content: center;
  margin-top: 30px;
}

.modal-buttons button {
  background: none;
  font-size: 1.6rem;
  color: #fff;
  padding: 8px 20px;
  margin-right: 20px;
  outline: none;
  border: 1px solid grey;
  border-radius: 100px;
  cursor: pointer;
}

.modal-buttons button:last-child {
  background-color: #ff1a55;
  border: 1px solid #ff1a55;
}

.modal-enter {
  opacity: 0;
}

.modal-leave-active {
  opacity: 0;
}

.modal-enter .modal-container,
.modal-leave-active .modal-container {
  -webkit-transform: scale(1.1);
  transform: scale(1.1);
}

@media only screen and (max-width: 1300px) {
  .modal-container {
    width: 50%;
  }
}
</style>
