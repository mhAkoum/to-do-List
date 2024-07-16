<template>
    <div>
        <h1 class="title">Your Productivity Partner</h1>
        <input type="text" class ="todo-input" placeholder="add task" v-model="newTodo" @keyup.enter ="addTodo">
        <div v-for="(todo, index) in todos" :key="todo.id" class="todo-item">
            <input type="checkbox" v-model= "todo.completed">
            <div class="todo-items-left">
                <div v-if="!todo.editing" @dblclick="editTodo(todo)" class="todo-item-label" :class="{ completed : todo.completed }">{{ todo.title }} </div>
                <input v-else class="todo-item-edit" type="text" v-model="todo.title" @blur ="DoneEdit(todo)"  @keyup.enter ="DoneEdit(todo)"> 
            </div>
        <div class ="remove-item" @click="removeTodo(index)" >
            &times;
        </div>
    </div>
    

    <div class="extra-container">
         <div><label><input type="checkbox" :checked="!anyRemaining" @change="checkAllTodos" >Check All</label></div> 
          <div> {{ remaining }} items left</div> 
          </div>
          </div>


  </template>
  
  <script>
  export default {
    name: 'todo-list',
    data () {
      return {
        newTodo: '',
        idForTodo: 3,
        todos: [
            {
                'id': 1,
                'title': 'to check Akoum s technical skills',
                'completed': false,
                'editing': false,

            },
            {
                'id': 2,
                'title': 'to accept Akoum in cleed.ai ',
                'completed': false,
                'editing': false,
            },
        ]
      }
    },

    computed: {
        remaining () {
            return this.todos.filter(todo => !todo.completed).length
        },
        anyRemaining () {
            return this.remaining != 0
        },
    },

    methods: {
        addTodo() {

            if (this.newTodo.trim().length == 0){
                return
            }
            this.todos.push({
                id: this.idForTodo,
                title: this.newTodo,
                completed: false,
                editing: false,
            })
            this.newTodo = ''
            this.idForTodo += 1
        },

        removeTodo(index){
            this.todos.splice(index, 1)
        },

        editTodo(todo){
            todo.editing = true
        },
        DoneEdit(todo){
            todo.editing = false
        },
        checkAllTodos (){
            this.todos.forEach( (todo) => {
                return todo.completed = event.target.checked;
            })
        }
    }
}

  </script>
  
  <style>
  .title{
    font-size: 20px;
    font-weight: bold;
    text-align: center;
  }
  .todo-input{
    width: 100%;
    padding: 10px 18px;
    font-size: 18px;
    margin-bottom: 16px;
    &:focus {
        outline: 8;
    }
  }
  .todo-item {
    margin-bottom: 10px;
    display: flex;
    align-items: center;
    justify-content: space-between
}
    .remove-item {
    cursor: pointer;
    margin-left: 10px;
    &shover {
    color: black;
    }
}

    .todo-iten-left {
    display: flex;
    align-items: left;
}
    .todo-iten-label {
    padding: 10px;
    border: 1px solid white;
    margin-left: 12px;
}

    .todo-item-edit {
    font-size: 16px;
    color: #022384;
    margin-left: 12px;
    width: 100%;
    padding: 10px;
    border: 1px solid #ccc;
    font-family: 'Avenir', Helvetica, Arial, sans-serif;

    &:focus {
        outline: none;
    }
}

.completed {
    text-decoration: line-through;
    color: #f87d6f;
}

.extra-container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    font-size: 16px;
    border-top: 1px solid lightgrey;
    padding-top: 14px;
    margin-bottom: 14px;
}
.button {
    font-size: 14px;
    background-color: white;
    appearance: none;
    &:hover {
        background: #022384;
    }
    &:focus {
        outline: none;
    }
}

.active {
    background: #022384;
}

  </style>
  