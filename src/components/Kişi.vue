<template>
  <div class="sayfa-baslık"><h1>Gramaj</h1></div>

  <div class="kişisayısı">
    <lable>Kişi sayısı:</lable>
    <select v-model="seçilen">
      <option value="">boş</option>
      <option>1</option>
      <option>2</option>
      <option>4</option>
      <option>6</option>
      <option>8</option>
      <option>12</option>
      <option>16</option>
      <option>20</option>
    </select>
  </div>

  <div class="gramaj">
    <ol>
      <li v-for="eleman in ürün" v-bind:key="eleman">
        {{ eleman.ad }} :<span v-if="eleman.gram * seçilen > 999"
          >{{ (eleman.gram * seçilen) / 1000 }}kg</span
        ><span v-else>{{ eleman.gram * seçilen }}gr</span>
      </li>
    </ol>
  </div>
</template>

<script>
export default {
  name: "Kişi",
  data() {
    return {
      ürün: [
        {
          ad: "Kako",
          gram: 50,
        },
        {
          ad: "Un",
          gram: 100,
        },
        {
          ad: "Yağ",
          gram: 180,
        },
        { ad: "Şeker", gram: 170 },
      ],
      seçilen: "",
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
