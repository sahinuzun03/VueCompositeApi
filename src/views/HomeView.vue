<template>
  <div class="home">
    <p>{{ name }} - {{ job }}</p>
    <button @click="clicked">Tıkla</button>
    <input type="text" v-model="name"> 
    <!-- Burada v-model name olarak direk bağlayabilirim name.value dememe gerek yoktur. -->
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

    let name = ref("Varol");

    const clicked = () => {
      name.value = "Deneme Click" //Değiştirmek için name'in value değerini değiştirmem lazım
      console.log(name);
    }
    return {name,clicked}; 
    }
  }
</script>
