<template>
  <div class="container">
    <div v-if="showMessage">
      <h1>{{ heading }}</h1>
      <p>{{ paragraph }}</p>
    </div>
    <ButtonOne @btnClick="toggleMessage" :text="text" :color="defaultColor" />
  </div>
</template>

<script>
import ButtonOne from "./components/ButtonOne";
import Message from "./components/Message";
export default {
  name: "App",
  components: { ButtonOne, Message },
  data() {
    return {
      text: "open one",
      heading: "Option Api",
      paragraph: "Button one with option api",
      showMessage: false,
      defaultColor: "#72aee6",
      btnClicked: 0,
    };
  },
  mounted() {
    console.log("component has mounted");
  },
  methods: {
    toggleMessage() {
      this.showMessage = !this.showMessage;

      this.btnClicked++;
      if (this.btnClicked === 5) {
        console.log("button has been clicked five times");
      }
    },
  },
};
</script>

<style scope>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap");
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  background: #f2f2f2;
}
.container {
  max-width: 500px;
  margin: 30px auto;
  min-height: 300px;
  padding: 30px;
  border-radius: 5px;
  background-color: white;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
