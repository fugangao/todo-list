<template>
  <div>
    <h2>App组件</h2>
  </div>
  <TodoInput @add="addNewTask" :list="taskList"></TodoInput>
  <TodoList :list="btnTask"></TodoList>
  <TodoButton v-model:active="activeIndex"></TodoButton>
</template>

<script>
import TodoList from './components/todo-list/TodoList.vue'
import TodoInput from './components/todo-input/TodoInput.vue'
import TodoButton from './components/todo-button/TodoButton.vue'
export default {
  name: 'MyApp',
  data() {
    return {
      taskList: [
        { id: 1, task: '下午去听课', done: true },
        { id: 2, task: '晚上去听音乐会', done: false },
        { id: 3, task: '星期三去聚会', done: false },
      ],
      nextId: 4,
      activeIndex: 0,
    }
  },
  components: {
    TodoList,
    TodoInput,
    TodoButton
  },
  methods: {
    addNewTask(task) {
      this.taskList.push({
        id: this.nextId, task: task, done: false 
      })
      this.nextId ++
    }
  },
  computed: {
    btnTask() {
      switch (this.activeIndex) {
        case 0:
        return this.taskList          
        case 1:
          return this.taskList.filter(x => x.done)
        case 2: 
          return this.taskList.filter(x => !x.done)
      }
    }
  }
}
</script>

<style lang="css" scoped>

</style>
