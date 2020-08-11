<template>
<div>
  <q-layout view="hHh LpR lfr" style="background-color: #212121; color: #FF4235;">
    <q-header reveal>
      <q-toolbar class="shadow-0" :style="$q.dark.isActive ? 'background-color: #212121;' : 'bg-white'">
        <q-btn
          @click="left = !left"
          dense
          round
          flat
          icon="menu"
          class="q-mr-sm "
        />
          <!-- :style="$q.dark.isActive ? '' : ''" -->
        <q-btn
          @click="$q.dark.toggle()"
          flat
          round
          dense
        >
          <img class="img-logo" :src="$q.dark.isActive ? require('../assets/your-trans-5.png') : require('../assets/your-trans-7.png')">
        </q-btn>
         <q-space/>
         <div class="">
         </div>
        <q-btn
          @click="right = !right"
          dense
          round
          flat
          icon="menu"
          class="q-mr-sm "
          :style="$q.dark.isActive ? '' : ''"
        >
        </q-btn>
      </q-toolbar>
      <q-toolbar class="q-pa-none" :style="$q.dark.isActive ? 'background-color: #212121; ' : 'background-color: #FFFFFF; '">
        <q-space />
        <q-tabs>
          <q-route-tab name="home" label="Início" to="/" />
          <q-route-tab name="about" label="Sobre" to="/about" />
          <q-route-tab name="services" label="Serviços" to="/services" />
          <q-route-tab name="doubts" label="Dúvidas" to="/doubts" />
        </q-tabs>
      </q-toolbar>
    </q-header>
     <q-drawer flat content-class="bg-white" bordered :width="250" v-model="left" side="left">
      <LeftDrawer/>
    </q-drawer>
    <q-drawer content-class="bg-white" bordered mini :width="65" v-model="right" side="right">
      <RightDrawer/>
    </q-drawer>
    <q-page-container>
      <div
        v-if="this.$route.fullPath != '/'"
        class="q-px-xl bg-grey-10 fit row wrap justify-center items-start content-center"
        :class="this.$route.fullPath.search(/\bios\b/) >= 0 ? '' : 'inset-shadow '"
      >
        <div class="q-pt-xs col-auto text-center text-white">
          <q-tabs dense class="text-white" no-caps>
            <q-tab
              @click="dynamicRoute('')"
              icon="mdi-web"
              label="Web"
            />
            <q-tab
              @click="dynamicRoute('/ios')"
              icon="mdi-apple-ios"
              label="iPhone"
            />
            <q-tab
              @click="dynamicRoute('/android')"
              icon="mdi-google-play"
              label="Android"
            />
            <q-tab
              @click="dynamicRoute('/mac')"
              icon="mdi-apple"
              label="Mac"
            />
            <q-tab
              @click="dynamicRoute('/windows')"
              icon="mdi-microsoft"
              label="Windows"
            />
          </q-tabs>
        </div>
      </div>
      <div
        v-else
        class="q-pa-xl bg-grey-10 fit row wrap justify-center items-start content-center"
        :class="this.$route.fullPath.search(/\bios\b/) >= 0 ? '' : 'inset-shadow '"
      >
        <div class="col-auto text-center text-white">
          <img class="img-logo" :src="require('../assets/your-trans-4.png')">
            <div class="text-subtitle1"><strong>Criando um </strong><strong style="color: #a587ff;">único</strong>
              <strong> produto, presente em todas as </strong><strong style="color: #a587ff;">plataformas.</strong></div>
              <br>
              <div class="text-weight-bolder text-h6">
                Celulares / Tablets - iOS / Android
              </div>
              <div class="q-pb-none text-weight-bolder text-h6">
                Computadores / Web - MacOS X / Windows
              </div>
              <q-tabs no-caps>
                <q-route-tab icon="mdi-web" label="Web" to="/" />
                <q-route-tab icon="mdi-apple-ios" label="iPhone" to="/ios" />
                <q-route-tab icon="mdi-google-play" label="Android" to="/android" />
                <q-route-tab icon="mdi-apple" label="Mac" to="/mac" />
                <q-route-tab icon="mdi-microsoft" label="Windows" to="/windows" />
              </q-tabs>
              <DynamicCard/>
            <div>
          </div>
        </div>
      </div>
      <router-view />
      <whatsapp/>
      <q-page-sticky v-if="$store.state.walle.showWallE" :offset="[0, 0]">
        <WallE/>
      </q-page-sticky>
    </q-page-container>
    <q-footer class="bg-grey-10" container style="height: 250px">
      <q-toolbar class="q-pa-lg">
        <img class="footer-logo" :src="require('../assets/your-trans-5.png')">
        <q-space/>
      </q-toolbar>
    </q-footer>
  </q-layout>
</div>
</template>

<script>
import LeftDrawer from '../components/drawers/LeftDrawer'
import RightDrawer from '../components/drawers/RightDrawer'
import whatsapp from '../components/whatsapp/DynamicWhatsapp'
import WallE from '../components/animations/WallE'

export default {
  components: {
    LeftDrawer,
    RightDrawer,
    whatsapp,
    WallE
  },
  data () {
    return {
      left: false,
      right: false,
      onClick: false,
      routeHomeVal: false,
      showWallE: true
    }
  },
  methods: {
    dynamicRoute (val) {
      const about = 'about'
      const services = 'services'
      const doubts = 'doubts'
      if (this.$route.fullPath.search(/\babout\b/) >= 0) {
        this.$router.push(val + '/' + about)
      } else if (this.$route.fullPath.search(/\bservices\b/) >= 0) {
        this.$router.push(val + '/' + services)
      } else if (this.$route.fullPath.search(/\bdoubts\b/) >= 0) {
        this.$router.push(val + '/' + doubts)
      } else {
        this.$router.push(val)
      }
    }
  }
}
</script>

<style>
</style>
