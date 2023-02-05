<template>
  <div class="home">
    <p>{{ name }} - {{ job }}</p>

    <p ref="info">Deneme</p>
    <!-- yukarıda ki p tagi komple benim info.value'nun değeri olmuş oldu. -->
    <button @click="clicked">Tıkla</button>
  </div>
</template>

<script>
//Setup içerisinde çağırmak için kullandık.
import { ref } from 'vue';

//ref referans bir değer oluşturmak için kullanıyoruz

export default {
  name: 'HomeView',
  components: {
  },
  setup(){
    let name="Şahin"
    let job = "Software Developer"

    const info = ref(null);//bir fonksiyon ilk değer olarak null veriyorum

    //Bu info'yu yukarıda bir yerde kullanacaksam bunu return etmem gerekiyor eğer yukarıda bir yerde kullanmayacaksam eğer return etmeme gerek yoktur.

    const clicked = () => {
      // console.log("Butona Tıklandı");

      console.log(info , info.value);
    }
    return {name,job,clicked,info}; 
    }
  }
</script>
