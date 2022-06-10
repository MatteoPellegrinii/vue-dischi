<template>
<div class="disc">
    <img :src="discobject.poster" :alt="discobject.title">
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
</style>