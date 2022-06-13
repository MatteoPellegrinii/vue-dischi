<template>
<div >
    <div class="contenitore" >
       <SelectType @search ="selectgenre" />

        <DischiCard
        v-for="(item, index) in filteredGenre"
        :key="index"
        :discobject="item"
      />
    </div>
    <div class="loading" v-if="castDisc == false" >LOADING...</div>
    
</div>
</template>

<script>
import axios from 'axios'
import DischiCard from './DischiCard.vue';
import SelectType from './SelectType.vue';

export default {
    name: 'DischiList',
    components: {
    DischiCard,
    SelectType,
},
 data() {
    return {
      apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
      castDisc: [],
      userChoose: "TUTTI",
    };
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
        },
            selectgenre(GenreSelected) {
        this.userChoose = GenreSelected;
        console.log(this.userChoose);
        },
    },
    computed: {
            filteredGenre() {
                console.log(this.userChoose);
                if (this.userChoose === "TUTTI") {
                    return this.castDisc;
                } else {
                    return this.castDisc.filter((item) => {
                    return item.genre
                        .toLowerCase()
                        .includes(this.userChoose.toLowerCase());
                    });
                }
                },
    }
}
</script>

<style scoped lang="scss">
.selection{
    width: 100%;
}
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