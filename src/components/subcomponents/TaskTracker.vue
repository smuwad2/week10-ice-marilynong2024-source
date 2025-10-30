<script>
    // TODO: Complete the code
    export default { 
        props: {
            task: Object,
            idx: Number
        },
        methods: {
            doneTask() {
                this.$emit('done', this.idx)
            }
        }
        // Hint: insert properties task (Object) and idx (Number)
    }
</script>

<template>
    <!-- TODO: add your template code here --> 
<div class="card" style="width: 18rem;">
    <!-- <img src="..." class="card-img-top" alt="..."> -->
    <div class="card-body">
        <h5 class="card-title">Deadline: {{ task.deadline }}</h5><hr>
        <p class="card-text">{{ task.desc }}</p>
        <!-- <a href="#" class="btn btn-primary">Go somewhere</a> -->
        <button class="btn btn-primary" @click="doneTask">Done</button>
  </div>
</div>
   
</template>


