<script setup>
    // Import Task Tracker component
    import taskTracker from './subcomponents/TaskTracker.vue'
</script>


<script>
    export default {
        data() {
            return {
                desc: '',
                deadline: '',
                taskList: []
            }
        },
        methods: {
            add() {
                this.taskList.push( { 'desc': this.desc, 'deadline': this.deadline } )
                this.desc = ''
                this.deadline = ''
            },
            // TODO: Add a new method, to delete a task completed
            deleteTask(idx) {
                this.taskList.splice(idx, 1);
            }
            
        },
        components: {
            taskTracker
        }
    }

</script>

<template>
    <div class="mb-3">
        <label for="desc" class="form-label">Task</label>
        <input type="text" class="form-control" id="desc" v-model='desc' placeholder="task">
    </div>
    <div class="mb-3">
        <label for="deadline" class="form-label">Deadline</label>
        <input type="date" class="form-control" id="deadline" v-model='deadline' placeholder="deadline">
    </div>

    <button type="button" @click="add" class="btn btn-primary">Add New Task</button>
    <hr>

    <!-- TODO: Modify following code -->
    <div class="d-flex flex-wrap">
        <task-tracker
            v-for="(task, index) in taskList"
            :task="task"
            :idx="index"
            :key="index"
            @done="deleteTask"
        ></task-tracker>
        <!-- the left (ie :task, :idx) is the name of the prop expected by the child component
             the right (ie task, index) is the value from the parent (ie task in v-for="(task, idx) in taskList")) -->
    </div>

</template>

<style scoped>
   
</style>
