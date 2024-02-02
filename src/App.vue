<script>

export default {
  name: "App",
  data() {
    return {
      isHome: true,
      pClass: ["title"],
      nome: 'jon snow',
      itsTrue: true,
      user: {
            first_name: 'Jon',
            last_name: 'Snow'
        },
      players: '',
      // colors recebe array para o checkbox funcionar
      colors: [],
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
  }],
  name: '',
  pageCount: 5,
    };
  },
  beforeCreate(){
    console.log('beforeCreate');
    console.log('Estado: ', this.nome);
    console.log('DOM: ', this.$el);
  },
  created(){
    console.log('created');
    console.log('Estado: ', this.nome);
    console.log('DOM: ', this.$el);
},
beforeMount(){
  console.log('beforeMount');
    console.log('Estado: ', this.nome);
    console.log('DOM: ', this.$el);
},
mounted(){
    window.addEventListener('resize', this.resize);
},
beforeUnmount(){
  window.removeEventListener('resize', this.resize);
},
unmounted(){
  console.log('unmounted');
    console.log('Estado: ', this.nome);
    console.log('DOM: ', this.$el);
},
  watch: {
    name() {
      this.saveUserName();
    },
    pageCount() {
      this.changePage();
     
    }
   
  },
  methods: {
    changeName() {
      this.itsTrue = !this.itsTrue;
      if(this.itsTrue){
        this.nome = 'joao';
      } else {
        this.nome = 'jon snow';
      }
      
    },
    onMouseOver($evt){
        console.log('mouse over', $evt);
    },
    onKeyUp($evt){
      console.log('key up', $evt);
    },
    saveUserName(){
      console.log(this.name);
    },
    changePage(){
      console.log('page changed');
    },
    resize($evt){
      console.log($evt);
    }
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
};

</script>

<template>
  <div>
  <h1 :class="pClass">salve</h1>
  <p :style="{ 'color': 'aqua' }">make it</p>


  <div>
    <label>Nome</label> <br>
    <input v-model="nome" type="text"> <br>
    {{ nome }}
    <button @click="changeName()">mudar nome</button>
  </div>
  <br>
  <h2>Jogadores:</h2>
  <select v-model="players">
      <option value="">Escolha um jogador</option>
      <option value="garnacho">Garnacho</option>
      <option value="antony">Antony</option>
      <option value="rashford">Rashford</option>
  </select> <br> <br>
  <h2>Jogador Escolhido: </h2>{{ players }}


  <input 
  v-model="colors"
  value="Amarelo"
  type="checkbox"> Amarelo

  <input 
  v-model="colors"
  value="Azul"
  type="checkbox"> Azul
  <br>
  {{ colors }}
<br>
 <!-- modificador de evento // event handler -->
  <button @mouseover.once="onMouseOver">Botão</button>
<br>
 <!-- keyboard event .enter só dispara quando aperta enter -->
  <input type="text" @keyup.enter="onKeyUp">

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

<input type="text" v-model="name"> <br>
<span>{{ name }}</span>
<br><br>
<select v-model="pageCount">
<option value="5">5</option>
<option value="10">10</option>
<option value="15">15</option>
</select> <br>
{{ pageCount }}
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
