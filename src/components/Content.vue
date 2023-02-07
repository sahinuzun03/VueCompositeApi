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
import { log } from 'console';
import { ref } from 'vue';
export default {
    props:['contents'],
    setup(){
        const contents = ref([]);
        const err = ref(null);
        const getContents = async () => {
            let data = await fetch('https://jsonplaceholder.typicode.com/posts');
            contents.value = await data.json();

            try {
                if(!data.ok){
                throw new Error('Verilere Erişilemedi!!!"')
            }
            } catch (error) {
                err.value = error.message;
            }
        }

        getContents();
        return {contents,err}
    }
}
</script>

<style>

</style>
