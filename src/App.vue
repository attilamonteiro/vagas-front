<template>
  <div>
    <h1>Componente App</h1>
    <!-- <p>App - Propriedade $style: {{ $style }}</p> -->
     <button @click="desmontarComponente()">Desmontar Componente</button>
    <topo-padrao />
    <conteudo v-if="visibilidade" />  
  </div>
</template>

<script>
import Conteudo from '@/components/layouts/Conteudo.vue';
import TopoPadrao from '@/components/layouts/TopoPadrao.vue';

export default {
  name: 'App',
  data: () => ({
    visibilidade: true
  }),

  methods: {
    desmontarComponente() {
      this.visibilidade = false;
    }
  },
  
  components: {
    Conteudo,
    TopoPadrao
  }

}
</script>

<style module>

</style>
