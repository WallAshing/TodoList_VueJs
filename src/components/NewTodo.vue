<template id="NewTodo">
    <div id="NewTodo">
        <div class="group">      
            <input class="taskInput" v-model="task" type="text" required>
            <span class="highlight"></span>
            <span class="bar"></span>
            <label class="taskLabel">Nouvelle tâche...</label>
        </div>
        <button @click="sendInput(task)" class="addingButton">
            <p>+</p>
        </button>
    </div>
</template>

<script>
export default {
    name: "NewTodo",
    data() {
        return{
            task: '',
        }
    },

    methods: {
        sendInput(task){
            if(task != '' || task != undefined){
                this.$emit("addToList", task)
            }
        }
    }
    
}
</script>