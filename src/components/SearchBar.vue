<template>
    <div>
        <input type="text" placeholder="Search" v-model="keywordSearch">
        <button @click="$emit('search', keywordSearch)">Search</button>
    </div>
</template>

<script>
export default {
    data(){
        return{
            keywordSearch:''
        }
    }
}
</script>

<style lang="scss" scoped>

</style>