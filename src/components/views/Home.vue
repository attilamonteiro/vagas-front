<template>
  <div class="container py-4">
    <div class="row">
      <div class="col">
        <PesquisarVaga />
      </div>
    </div>
    <div class="row mt-5" v-for="(vaga, index) in vagas" :key="index">
      <div class="col">
        <vaga v-bind="vaga" />
      </div>
    </div>
    <div class="row mt-5">
      <div class="col-4">
        <indicador titulo="Vagas Abertas" indicador="100" bg="bg-dark" color="text-white" />
      </div>
      <div class="col-4">
        <indicador titulo="Profissionais cadastrados" indicador="225" bg="bg-dark" color="text-white" />
      </div>
      <div class="col-4">
        <indicador titulo="Visitantes online" :indicador="usuariosOnline" bg="bg-light" color="text-dark" />
      </div>
    </div>
  </div>
</template>

<script>
import Indicador from '@/components/comuns/Indicador.vue'
import PesquisarVaga from '@/components/comuns/PesquisarVaga.vue'
import Vaga from '@/components/comuns/Vaga.vue'

export default {
  name: 'Home',
  components: {
    PesquisarVaga,
    Indicador,
    Vaga
  },
  data: () => ({
    usuariosOnline: 0,
    vagas: []
  }),
  methods: {
    getUsuarioOnline() {
      this.usuariosOnline = Math.floor(Math.random() * 101)
    }
  },
  mounted() {
    this.vagas = JSON.parse(localStorage.getItem('vagas'))
  }
}
</script>

<style scoped></style>
