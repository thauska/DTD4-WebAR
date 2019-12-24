<template>
<q-page-container>
  <q-page padding class="flex justify-center">
    <div class="q-pa-md">
      <div class="column items-center">
        <div class="col q-mb-sm">
          <img alt="Data Tech Day logo" src="statics/images/dtd.png" width="150px" >
        </div>
        <div class="col q-pt-md">
          <p class="text-h4 text-bold text-black text-center">Realidade Aumentada na Web</p>
        </div>
        <div class="col text-justify">
          <p class="text-body1">Para instrução de utilização, clique no botão<q-btn flat round dense icon="info" />da barra de navegação.</p>
        </div>
        <div class="col q-pa-md">
          <q-btn color="dark" glossy
            class="q-mt-xs text-no-wrap"
            push
            label="Iniciar realidade aumentada"
            @click="routeModify()"/>
        </div>
      </div>
    </div>
  </q-page>
</q-page-container>
</template>

<script>
export default {
  name: 'PageIndex',
  methods: {
    routeModify () {
      this.$router.push({ name: 'aframe' })
    }
  }
}
</script>

<style scoped>
@media (min-width: 768px) {
  .text-h4 {
    font-size: 2rem
  }
}
@media (max-width: 768px) {
  .text-h4 {
    font-size: 1.8rem
  }
}
</style>
