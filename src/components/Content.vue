<template>
    <div>
        <div v-for="content in contents" :key="content.id">
            {{ content.title }}
        </div>
        <div v-if="err">
            {{ err }}
        </div>
    </div>
</template>

<script>
import { ref } from 'vue';
import getContentsFetch from '../composables/getContentsFetch';
import {useRoute,useRouter} from 'vue-router'
export default {
    setup(){
        const route = useRoute();
        const router = useRouter();

        //route : route ile gönderilen parametreleri göndermek için kullanılır
        console.log('Route :' , route);

        //router : route içerisindeki metotlar gelir ileri git geri git.
        console.log('Router : ' , router);
        




        //Aşağıdaki tanımlamaların hepsinin getContentFetch içerisinden geleceğini söyledim.
        const {contents,err,getContents} = getContentsFetch();
        getContents();//Yukarıdaki tanımlamayı kullanmış oldum
        return {contents,err} //Bunlarıda zaten yukarıdan kullanmış oldum
    }
}
</script>

<style>
/* Composoble dosya yukarıda yazdığım kodu süreli çağırıp çağırıp kullanmak istediğim zaman çağırdığımız dosya yapısını ifade etmektedir.Yukarıdaki kod components gibi bir yapı haline getireceğiz. */
</style>
