<template>
<div>
    <div @click="deleteItem">{{content}}</div>
</div>
</template>
<script>
export default {
    props:['content','index'],
    methods:{
        deleteItem(){
            this.$emit('delete',this.index)
        }
    }
};
</script>
<style>
</style>


