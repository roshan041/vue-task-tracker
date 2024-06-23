<template>
    <header>
        <h1>{{title}}</h1>
        <Button @toggle-add-task="$emit('toggle-add-task')" :btnText="showAddTask ?'close':'Add Task'" :btnColor="showAddTask ?'green':'blue'"/>
    </header>
</template>

<script>
import Button from './Button.vue'

export default{
    name:'Header',
    props:{
        title:String,
        showAddTask:Boolean,
    },
    components:{
        Button
    }
}
</script>

<style scoped>
    header {
        display: flex;
        align-items: center;
        margin-bottom: 20px;
    }
</style>
