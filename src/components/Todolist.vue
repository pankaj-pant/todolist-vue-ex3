<template>
    <div>
        <input type="text" placeholder="Task" v-model="description.task"/>
        <input type="date" placeholder="Date" v-model="description.date"/>
        <button v-on:click="add">Add</button>
        <table>
            <tbody>
                <tr v-for="(todo, index) in todos" v-bind:key="index">
                    <td>{{todo.task}}</td>
                    <td>{{todo.date}}</td>
                </tr>
            </tbody>    
        </table>
    </div>
</template>

<script>

export default {
    name: 'Todolist',
    data() {
        return {
            description: {task: "", date: ""},
            todos: []
        }
    },
    methods: {
        add: function() {
            this.todos.push(this.description);
            this.description={task: "", date: ""};
        }
    }
}
</script>

<style scoped>
table {
    margin: auto
}
</style>