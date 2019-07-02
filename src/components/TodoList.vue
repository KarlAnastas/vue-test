<template>
  <div>
    <BaseInputText
      v-model="newTodoText"
      placeholder="New todo"
      @keydown.enter="addTodo"
    />
    <ul v-if="todos.lenght">
      <TodoListItem
        v-for="todo in todos"
        :key="todo.id"
        :todo="todo"
        @remove="removeTodo"
      />
    </ul>
    <p v-else>
      Nothing left in teh list. Add a new todo in the input abover.
    </p>
  </div>
</template>

<script>

import BaseInputText from './BaseInputText.vue'
import TodoListItem from './TodoListItem.vue'

let nextTodoId = 1

export default {
  name: 'TodoList',
  props: {
    msg: String
  }
}

export default {
  components: {
    BaseInputText, TodoListItem
  },
  data () {
    return {
      nextTodoText: '',
      todos: [
        {
          id: nextTodoId++,
          text: 'Learn Vue'
        },
        {
          id: nextTodoId++,
          text: 'Learn about single-file components'
        },
        {
          id: nextTodoId++,
          text: 'Fall in love'
        }
      ]
    }
  },
  methods: {
    addTodo () {
      const trimmedText = this.newTodoText.trim()
      if (trimmedText) {
        this.todos.push({
          id: nextTodoId++,
          text: trimmedText
        })
        this.newTodoText = ''
      }
    },
    removeTodo (idToRemove) {
      this.todos = this.todos.filter(todo => {
        return todo.id !== idToRemove
      })
    }
  }
}
</script>

