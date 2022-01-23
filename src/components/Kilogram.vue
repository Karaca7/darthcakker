<template>
  <h1>Kilogram</h1>
  <p>
    Bu sayafada kilogram girip ürün elemanlarının gramajlarını listeyeleceğim
  </p>
  <p>+Bence vue öğrenmek için ideal bir proje olacak</p>
  <p>css e aldırmayın nasıl kullanmam gerektiğini biliyorum</p>
</template>

<script>
export default {
  name: "Kişi",
  data() {
    return {
      ürün: [
        {
          ad: "Kako",
          gram: 25,
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
