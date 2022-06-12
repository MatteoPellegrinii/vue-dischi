<template>
<div >
    <div class="contenitore" >
        <DischiCard v-for="(item, index) in castDisc" :key="index"
     :discobject= "item"
     /></div>
     <div class="loading" v-if="castDisc == false" >LOADING...</div>
    
</div>
</template>

<script>
import axios from 'axios'
import DischiCard from './DischiCard.vue';

export default {
    name: 'DischiList',
    components: {
    DischiCard
},
    data(){
        return{
            apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
            castDisc: []
        }
    },
    created(){
        this.getDisc();
    },
    methods: {
        getDisc(){
            axios.get(this.apiUrl)
            .then(result =>{
            this.castDisc = result.data.response;
            console.log(result);
        })
        }
    }
}
</script>

<style scoped lang="scss">
.contenitore{
    display: flex;
    width: 60%;
    margin: auto;
    flex-wrap: wrap;
}
.loading{
    color: white;
}
</style>