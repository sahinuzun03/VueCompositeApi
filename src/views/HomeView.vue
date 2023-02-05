<template>
  <div class="home">
    HOME
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
    console.log("Setup Yüklendi");
    //Component oluşmadan önceki durum.İlk oluşturma aşamasında created'dan da önce çalışıyor.
    onMounted(() => {
      console.log("Mounted setup içerisinde çalıştırıldı.");
    })
  },
}
</script>
