<template>
    <button @click="btnClick()" :style="{background:btnColor}" class="btn"  >{{btnText}}</button>
</template>

<script>
export default{
    name:'Button',
    props:{
        btnText:String,
        btnColor:String,
    },
    methods:{
        btnClick(){
            //console.log("btn clicked")
            this.$emit('toggle-add-task')
        }
    }
}
</script>
