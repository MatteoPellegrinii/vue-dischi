<template>
    <div class="disc">
    <img :src="discobject.poster" :alt="discobject.title">
    <h3>{{discobject.title}} </h3>
    <h4>{{discobject.author}} </h4>
    <h5>{{discobject.genre}} </h5>
    <h6>{{discobject.year}} </h6>
</div>

</template>

<script>
export default {
    name: 'DischiCard',
    props: {
        discobject: Object
    }
}
</script>

<style scoped lang="scss">
.disc{
        width: calc(20% - 20px);
        margin: 10px;
        background-color: whitesmoke;
        img{
            width: 100%;
        }
    }
</style>