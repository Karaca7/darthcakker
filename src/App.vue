<template>
  <div class="contentbig"><h1>Darth Cakeker</h1></div>
  <header>
    <button v-for="tab in liste" :key="tab" @click="şimdikisayfa = tab">
      {{ tab }}
    </button>
  </header>

  <div class="container">
    <keep-alive>
      <component :is="startpage"></component>
    </keep-alive>
  </div>
</template>

<script>
import Kişi from "./components/Kişi.vue";
import Kilogram from "./components/Kilogram.vue";

export default {
  name: "App",
  data() {
    return {
      şimdikisayfa: "Kisi",

      liste: ["Kisi", "Kilogram"],
    };
  },

  methods: {
    tıkla() {
      console.log(this.şimdikisayfa);
    },
  },
  computed: {
    startpage() {
      console.log("tab-" + this.şimdikisayfa.toLowerCase());
      return "tab-" + this.şimdikisayfa.toLowerCase();
    },
  },

  components: {
    "tab-kisi": Kişi,
    "tab-kilogram": Kilogram,
  },
};
</script>

//
<style lang="scss">
// #app {
//   font-family: Avenir, Helvetica, Arial, sans-serif;
//   -webkit-font-smoothing: antialiased;
//   -moz-osx-font-smoothing: grayscale;
//   text-align: center;
//   color: #2c3e50;
//   margin-top: 60px;
// }
//
</style>
