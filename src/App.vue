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


