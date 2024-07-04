<template>
    <div>
      <h1>{{titulo}}</h1>
      <p>Conteudo - Propriedade $style: {{ $style }}</p>
      <!-- <div :class="$style.teste">Class Teste 1</div>
      <div :id="$style['teste-2']">ID Teste 2</div> -->
      <button @click="alterarTeste()">Alterar Teste</button>
      <home />
      <publicar-vaga />
    </div>
</template>
  
<script>
import Home from '@/components/views/Home.vue';
import PublicarVaga from '@/components/views/PublicarVaga.vue';

export default {
  name: 'Conteudo',
  components: {
    Home,
    PublicarVaga
  },
  data: () => ({
    teste: 'Teste',
    titulo: 'Conteudo'
  }),
  methods: {
    alterarTeste() {
      this.titulo += '*';
    }
  },
  beforeCreate() {
    console.log('beforeCreate - Conteudo', this.teste);
  },
  created() {
    console.log('created - Conteudo', this.teste);
  },
  beforeMount() {
    console.log('beforeMount - Conteudo', this.teste);
  },
  mounted() {
    console.log('mounted - Conteudo', this.teste);
  },
  beforeUpdate() {
    console.log('beforeUpdate - Conteudo', this.teste);
  },
  updated() {
    console.log('updated - Conteudo');
  },
  beforeDestroy() {
    console.log('beforeDestroy - Conteudo');
  },
  destroyed() {
    console.log('destroyed - Conteudo');
  }

}

</script>


<style module>

.teste {
  background-color: red
}
#teste-2 {
  background-color: green
}
</style>