<template>
        <div class="selection">
        <select name="GENERE" id="GENERE" @click="$emit('myselect', GenreSelected)"> 
            <option value="TUTTI">TUTTI</option> 
            <option value="ROCK">ROCK</option>
            <option value="POP">POP</option>
            <option value="METAL">METAL</option>
            <option value="JAZZ">JAZZ</option>
        </select>
        </div>
</template>

<script>
export default {
    name: 'SelectType',
    data(){
        return{
            GenreSelected: ""
        }
    }
}
</script>

<style scoped lang="scss">

</style>