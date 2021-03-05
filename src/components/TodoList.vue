<template id="TodoList">
<div class="container">
    <NewTodo @addToList="addToList"/>
    <ul>
        <li v-for="item in tasks" v-bind:class="{ deleted: item.deleted}" v-bind:key="item">
            <input v-on:click='checkTask(item.index)' class ="todoCheckbox" name="checkbox" type="checkbox">
            <label class="todoLabel" v-bind:class="{ striped: item.isStriped }" for="checkbox">{{ item.name }}</label>
            <button v-on:click='removeToList(item.index)' class="deletingButton">
                <img src="img/delete.png" alt="Poubelle">
            </button>
        </li>
    </ul>
</div>
</template>

<script>
import TodoCard from './TodoCard.vue'
import NewTodo from './NewTodo'
export default {
    name: "TodoList",
    data() {
        return{
            i: 0,
            tasks: [
            ],
        }
    },
    components:{
        NewTodo
    },
    methods: {
        addToList(input){
            let task = {
              name: input,
              index: this.i,
              deleted: false,
              isStriped: false,
            };
            console.log(task)
            this.tasks.push(task);
            TodoCard.taskNumber += 1;
            this.i += 1;
        },
        removeToList(index) {
            this.tasks[index].deleted = true
            TodoCard.taskNumber -= 1;
        },
        checkTask(index){
            let item = this.tasks[index]
            item.isStriped ? item.isStriped = false : item.isStriped = true;
        }
    },

}

</script>