<template>
  <div class="home">
    <p>{{ name }} - {{ job }}</p>
    <button @click="clicked">Tıkla</button>
  </div>
</template>

<script>
//Setup içerisinde çağırmak için kullandık.
import { onMounted } from 'vue';

export default {
  name: 'HomeView',
  components: {
  },
  setup(){
    let name="Şahin"
    let job = "Software Developer"

    const clicked = () => {
      console.log("Butona Tıklandı");
    }


    return {name,job,clicked}; 
    //Burada tanımlı dataları yukarıda kullanabilmek için return etmem gerekmektedir.Bunlar metot olsa dahi return etmem gerekmektedir.
    }
  }
</script>
