<template>
  <div class="container">
    <div v-if="showOptionApi">
      <h1>{{ heading }}</h1>
      <p>{{ paragraph }}</p>
    </div>
    <ButtonOne @btnClick="toggleOption" :text="text" :color="color" />
    <div v-if="showCompositionApi">
      <h1>{{ headingComp }}</h1>
      <p>{{ paraComp }}</p>
    </div>
    <ButtonTwo
      @btnClickTwo="toggleComp"
      :textTwo="textTwo"
      :colorTwo="colorTwo"
    />
  </div>
</template>

<script>
import { ref, context, onMounted, computed, reactive } from "vue";
import ButtonOne from "./components/ButtonOne";
import ButtonTwo from "./components/ButtonTwo";

export default {
  name: "App",
  components: { ButtonOne, ButtonTwo },
  data() {
    return {
      text: "open one",
      heading: "Option Api",
      paragraph: "button one with option api",
      showOptionApi: false,
      color: "#72aee6",
      btnClicked: 0,
    };
  },
  mounted() {
    console.log("component one has mounted");
  },
  methods: {
    toggleOption() {
      this.showOptionApi = !this.showOptionApi;

      this.btnClicked++;
      if (this.btnClicked === 5) {
        console.log("option api has been clicked five times");
      }
    },
  },
  setup(props, context) {
    const textTwo = ref("button two");
    const colorTwo = ref("#8a2424");

    const showCompositionApi = ref(false);
    const headingComp = ref("Compostion Api");
    const paraComp = ref("button two with composition api");
    const state = reactive({ btnTwoClicked: ref(0) });

    onMounted(() => console.log("component two has mounted"));

    const toggleComp = () => {
      showCompositionApi.value = !showCompositionApi.value;
      state.btnTwoClicked++;
      if (state.btnTwoClicked === 5) {
        console.log("composition api clicked five times");
      }
    };

    return {
      textTwo,
      colorTwo,
      showCompositionApi,
      headingComp,
      paraComp,
      toggleComp,
      state,
    };
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
  font-family: "Poppins", sans-serif;
}

h1 {
  margin: 20px auto;
}
.container {
  max-width: 500px;
  margin: 30px auto;
  min-height: 300px;
  padding: 30px;
  border-radius: 5px;
  background-color: white;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
}

.btn {
  display: block;
  margin: 40px auto 0;
  color: white;
  padding: 10px;
  border: 0;
  border-radius: 6px;
  font-size: 16px;
  cursor: pointer;
  box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
}

.btn.hovering {
  transform: scale(1.5);
}
</style>
