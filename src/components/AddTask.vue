<template>
    <form @submit="addTask" class="add-form">
    <div class="form-control">
      <label>Task</label>
      <input type="text" v-model="text" name="text" placeholder="Add Task" />
    </div>
    <div class="form-control">
      <label>Day</label>
      <input
        type="text"
        v-model="day"
        name="day"
        placeholder="Add Day"
      />
    </div>
    <div class="form-control form-control-check">
      <label>Set Reminder</label>
      <input type="checkbox" v-model="reminder" name="reminder" />
    </div>

    <input type="submit" value="Save Task" class="btn btn-block" />
  </form>
</template>

<script>
export default {
    name:'AddTask',
    data(){
        return{
            text:'',
            day:'',
            reminder:false,
            }
    },
    methods:{
        addTask(e){
            e.preventDefault()

            if(!this.text || !this.day){
                alert("enter all details")
                return
            }
            const newTask={
                id:Math.floor(Math.random()*100000),
                text:this.text,
                day:this.day,
                reminder:this.reminder
            }

            console.log(newTask)
            this.$emit('add-task',newTask)

            this.text=''
            this.day=''
            this.reminder=''

        }
    }
}
</script>

<style scoped>
.add-form {
  margin-bottom: 40px;
}
.form-control {
  margin: 20px 0;
}
.form-control label {
  display: block;
}
.form-control input {
  width: 100%;
  height: 40px;
  margin: 5px;
  padding: 3px 7px;
  font-size: 17px;
}
.form-control-check {
  display: block;
  align-items: center;
}
.form-control-check label {
    display:block
}
.form-control-check input {
  display:block
}
</style>