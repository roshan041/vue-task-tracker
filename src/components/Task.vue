<template>
    <div class="task" :class="[task.reminder?'reminder':'']">
        <h3>
        {{ task.text }}
         <i @click="taskDelete(task.id)" class="fas fa-times"></i>
        </h3>
        <h4>{{ task.day }}</h4>
  </div>
</template>

<script>
export default {
    name:'Task',
    props:{
        task:{

        },
    },
    methods:{
        taskDelete(id){
            //console.log("hi dlt",id)
            this.$emit('delete-task',id)
        }
    }
}
</script>


<style scope>
.fas {
  color: red;
}
.task {
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
}
.task.reminder {
  border-left: 5px solid green;
}
.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>