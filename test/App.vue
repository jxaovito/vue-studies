<script>

export default {
  name: "App",
  data() {
    return {
        user: {
            first_name: 'Jon',
            last_name: 'Snow'
        },
        todos: [{
            
  
    "userId": 1,
    "id": 1,
    "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
    "body": "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto"
  },
  {
    "userId": 1,
    "id": 2,
    "title": "qui est esse",
    "body": "est rerum tempore vitae\nsequi sint nihil reprehenderit dolor beatae ea dolores neque\nfugiat blanditiis voluptate porro vel nihil molestiae ut reiciendis\nqui aperiam non debitis possimus qui neque nisi nulla"
  },
  {
    "userId": 1,
    "id": 3,
    "title": "ea molestias quasi exercitationem repellat qui ipsa sit aut",
    "body": "et iusto sed quo iure\nvoluptatem occaecati omnis eligendi aut ad\nvoluptatem doloribus vel accusantium quis pariatur\nmolestiae porro eius odio et labore et velit aut"
  },
  {
    "userId": 1,
    "id": 4,
    "title": "eum et est occaecati",
    "body": "ullam et saepe reiciendis voluptatem adipisci\nsit amet autem assumenda provident rerum culpa\nquis hic commodi nesciunt rem tenetur doloremque ipsam iure\nquis sunt voluptatem rerum illo velit"
  }]
        
    };
  },
  computed: {
    fullName() {
        return `${this.user.first_name} ${this.user.last_name}`
    },
    uncompletedTodos() {
        return this.todos.filter(todo => !todo.completed);
    },
    completedTodos() {
        return this.todos.filter(todo => todo.completed);
    }
  },

  methods: {
   
  }
};

</script>

<template>
  <div>
    {{ fullName }}
    <br> <br>
    <h2>Todos em aberto</h2>
    <div v-for="todo in uncompletedTodos" :key="todo.id">
        {{ todo.title }} <span>{{ todo.completed }}</span>
    </div>
    <br>
    <h2>Todos completas</h2>
    <div v-for="todo in completedTodos" :key="todo.id">
        {{ todo.title }} <span>{{ todo.completed }}</span>
    </div>
    <br>
    <h2>Todos</h2>
    <div v-for="todo in todos" :key="todo.id">
    <input type="checkbox"
    v-model="todo.completed">
        {{ todo.title }}
</div>
</div>


</template>

<style scoped>
.titlehome {
  color: red;
}

.title {
  font-size: 40px;
  color: green;
}
</style>
