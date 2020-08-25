<template>
    <div id="task">
        <div class="task">
            <h3 class="task__title">Planned: {{tasks.length}}</h3>
            <input class="task__input" type="text" placeholder="Add a task due today" v-model="newTask" @keyup.enter="task_create()">
            <div class="task__item" v-for="(task, index) in tasks" :data="data" :key="index">
                <div>
                    {{task.title}}
                </div>
                
                <button class="task__remove" @click="task_remove(index)">
                    ✅
                </button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'task',
    data() {
        return {
            newTask: '',
            tasks: [
                {id: 1, title: 'Do something good', completed: false},
                {id: 2, title: 'Feed the cat', completed: false}
            ]
        }
    },
    methods: {
       task_create() {
           if (this.tasks.title != '') {
               this.tasks.push({
                   id: this.idTask,
                   title: this.newTask,
                   completed: false
               });
           }

           this.newTask = ''
           this.idTask++
       },
       task_remove(index) {
           this.tasks.splice(index, 1);
       },
    }
}
</script>

<style lang="sass">
.task
    width: 400px
    margin: 0 auto

.task__title
    font-size: 24px

.task__input
    width: 100%
    height: 30px
    font-size: 20px
    border: 1px solid #2c3e50
    outline: none
    color: #2c3e50
    box-sizing: border-box

.task__input::placeholder 
    color: #2c3e50

.task__item
    display: flex
    justify-content: space-between
    text-align: start
    margin-top: 20px
    padding-left: 8px

.task__remove
    border: none
    outline: none
    background-color: rgba(0, 0, 0, 0)
    cursor: pointer
</style>