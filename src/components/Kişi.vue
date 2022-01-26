<template>
  <div class="sayfa-baslık"><h1>Gramaj</h1></div>

  <div class="kişisayısı">
    <div>
      <span v-for="eleman in ürün" :key="eleman">
        <label>{{ eleman.ad }}</label
        ><input type="checkbox" name="eleman.ad" id="" v-model="eleman.block" />
      </span>
    </div>
    <hr />
    <span></span>

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
        <span v-if="eleman.block"
          >{{ eleman.ad }} :{{ hesapla(eleman.gram) }}</span
        >
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
          block: false,
        },
        {
          ad: "Un",
          gram: 100,
          block: false,
        },
        {
          ad: "Yağ",
          gram: 180,
          block: false,
        },
        { ad: "Şeker", gram: 170, block: false },
      ],
      seçilen: null,
    };
  },

  methods: {
    hesapla(gram) {
      gram = gram * this.seçilen;
      if (gram > 999) {
        return `${gram / 1000}kg.`;
      } else {
        return `${gram}gr.`;
      }
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
