<template>
  <div class="home">
    <Contents :contents="contents"></Contents>
    <!-- contents'e prop gönderdik -->
  </div>
</template>

<script>
//Setup içerisinde çağırmak için kullandık.
import { ref,computed,watch,watchEffect } from 'vue';
import Contents from '../components/Content.vue'

//ref referans bir değer oluşturmak için kullanıyoruz

export default {
  name: 'HomeView',
  components:{Contents},

  setup(){
    const contents = ref([
      {id:1,title:'Deneme 1',details:'Detail 1 '},{id:1,title:'Deneme 2',details:'Detail 2 '},
      {id:1,title:'Deneme 3',details:'Detail 3 '},
      {id:1,title:'Deneme 4',details:'Detail 4 '}]);

      return {contents}
    }
  }
</script>
