<template>
  <div class="home">
    <input type="text" v-model="search">
    <div v-for="day in finded" :key="day">
      {{ day }}
    </div>
  </div>
</template>

<script>
//Setup içerisinde çağırmak için kullandık.
import { ref,computed,watch,watchEffect } from 'vue';


//ref referans bir değer oluşturmak için kullanıyoruz

export default {
  name: 'HomeView',

  setup(){
    const days = ref(["Pazartesi","Sali","Çarşamba","Perşembe","Cuma"]);

    const search = ref("");
    const finded = computed(() => {
      return days.value.filter((day) => day.includes(search.value))
    })

    //search değiştikçe watch çalışmaya başladı
    const watchStop = watch(search,() => {
      console.log("watch çalıştı");
    })

    //Wathceffec hiçbir şey olmadanda bir kere çalıştı.
    const watchEffectStop = watchEffect(() => {
      console.log("watcheffect çalıştı",days.value);
      console.log("watcheffect çalıştı",search.value);
    });

    return {days,search,finded}
    }
  }
</script>
