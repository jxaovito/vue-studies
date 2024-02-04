<script>
import Header from './components/headerComponent.vue';
import Alert from './components/baseAlert.vue';
import Content from './components/contentComponent.vue';


export default {
  name: "App",
  components: { Header, Alert, Content },
  data() {
    return {
      isHome: true,
      itsTrue: true,
  variant: 'success',
  text: 'Seu formulário foi enviado'
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
  methods: {
  },
  computed: {
  },
};

</script>

<template>
  <div>
    <Content/>


<div><Header>
  <template v-slot:title>
    Home
  </template>
  <template v-slot:description>
    <p>coaskdpo</p>
  </template>
</Header></div>

<div>
  <Alert :variant="variant"/>
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
