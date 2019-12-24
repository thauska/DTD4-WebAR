<template>
  <q-layout view="hHh lpR fFf">
    <q-header bordered class="glossy bg-purple-8 text-white">
      <q-toolbar>
        <q-toolbar-title class="q-ml-md" clickable @click="home ()">
          <q-avatar size="35px">
            <img src="statics/app-logo-128x128.png">
          </q-avatar>
           Realidade Aumentada na Web
        </q-toolbar-title>
        <q-btn flat round dense icon="info" @click="dialog = true" />
      </q-toolbar>
    </q-header>

    <q-dialog v-model="dialog">
      <q-layout view="hHh lpR fFf" container class="bg-grey-3">
        <q-header bordered class="glossy bg-purple-8 text-white">
          <q-toolbar>
            <q-toolbar-title>
              Instruction
            </q-toolbar-title>
            <q-space />
            <q-btn icon="close" flat round dense v-close-popup />
          </q-toolbar>
        </q-header>

        <q-page-container>
          <q-page class="q-pa-md">
            <div class="column q-px-sm items-center">
              <div class="col q-pt-md">
                <img alt="AR logo" src="statics/app-logo-128x128.png" width="50px">
              </div>
              <div class="col">
                <p class="text-h4 text-bold q-pt-lg text-black">Instrução</p>
              </div>
              <div class="col text-justify">
                <p class="text-body1">
                  <strong>1 | </strong>Por favor, abra esta demonstração de RA na Web em um navegador web atualizado (recomendado: Google Chrome (somente Android), Safari (iOS 11+), Firefox, Microsoft Edge e Opera).
                </p>
                <p class="text-body1">
                  <strong>2 | </strong>Após clicar em INICIAR RA, você precisará autorizar a câmera do dispositivo e focá-la no marcador () , disponível para download logo abaixo.
                </p>
                <p class="text-body1">
                  <strong>3 | </strong>Fechando está demonstração de RA, removerá a Aplicação Web (PWA) completamente do seu dispositivo. Autorizando a "instalação" dele, o PWA continuará operando, inclusive offline.
                </p>
              </div>
              <div class="q-pa-md">
                <q-btn glossy icon="cloud_download" label="Baixar Marcador" class="text-nowrap" type="a" href="statics/marker/pattern-DTD.png" download target="_blank" />
              </div>
            </div>
          </q-page>
        </q-page-container>

        <q-footer bordered class="bg-white text-black">
          <q-toolbar>
            <q-toolbar-title>
               <small>&copy; {{ new Date().getFullYear() }} — <strong> <a href="https://github.com/thauska" target="_blank">Thayana Mamoré</a> </strong></small>
            </q-toolbar-title>
          </q-toolbar>
        </q-footer>
      </q-layout>
    </q-dialog>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { openURL } from 'quasar'

export default {
  name: 'MyLayout',
  data () {
    return {
      leftDrawerOpen: this.$q.platform.is.desktop,
      dialog: false,
      drawerLeft: false,
      drawerRight: true
    }
  },
  methods: {
    openURL,
    home () {
      window.location.href = '/'
    }
  }
}
</script>

<style lang="stylus" scoped>
.q-toolbar__title{
  font-size 18px
}

.q-btn {
  font-size 0.8rem
}

small {
  font-size 14px!important
}
a {
  text-decoration none
}
</style>
