<script>

export default {
  name: "App",
  data() {
    return {
      isHome: true,
      pClass: ["title"],
      nome: 'jon snow',
      itsTrue: true,
      players: '',
      // colors recebe array para o checkbox funcionar
      colors: []
    };
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
    }
  }
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
  <input type="text" @keyup.enter="onKeyUp"></input>
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
