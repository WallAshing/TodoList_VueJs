<template>
    <div id="TodoCard">
        <header>
          <p class="date">{{ today }}</p>
          <h2>VueJs Tutorial ToDo List</h2>
          <p class="task">{{taskNumber}} tâches</p>
        </header>
        <TodoList/>
    </div>
</template>

<script>
import TodoList from './TodoList.vue'
export default {
    name: "TodoCard",
    data() {
        return{
            taskNumber: 0,
        }
    },
    components:{
        TodoList,
    },
    computed: {
          today() {

            let options = { weekday: 'long'};
            let today = new Date();
            let jour = new Intl.DateTimeFormat('fr-FR', options).format(today);
            let dd = String(today.getDate()).padStart(2, '0');
            let mm = String(today.getMonth());
            let monthName = ["Janvier","Février", "Mars", "Avril", "Mai", "Juin", "Juillet", "Août", "Septembre", "Octobre", "Novembre", "Décembre"];
            let date = jour + " " + dd + " " + monthName[mm];
            return date;

          }
    },
}
</script>