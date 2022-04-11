<template>
  <div class="container">
    <div v-if="showMessage">
      <Message
        @toggle="toggleMessage"
        :heading="heading"
        :paragraph="paragraph"
      />
    </div>
    <ButtonOne text="open one" :color="defaultColor" />
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
      defaultColor: "#00ce89",
      heading: "Show Heading",
      paragraph: "Show Paragraph",
      showMessage: false,
    };
  },
  methods: {
    toggleMessage() {
      this.showMessage = !this.showMessage;
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

.btn {
  display: block;
  margin: 20px auto 0;
  color: white;
  padding: 10px;
  border: 0;
  border-radius: 6px;
  font-size: 16px;
  cursor: pointer;
  box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
}
</style>
