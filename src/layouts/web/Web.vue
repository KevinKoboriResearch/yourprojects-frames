<template>
<div>
    <q-layout
      view="hHh LpR lfr"
      style="color: #FF4235;"
      :style="$q.dark.isActive ?
        'background-color: ' + darkThemeBGColor + '; color: ' + darkThemeColor
        : 'background-color: ' + lightThemeBGColor + '; color: ' + lightThemeColor"
    >
      <q-header
        reveal
        class="transparent"
      >
        <q-toolbar
          :style="$q.dark.isActive ?
            'background-color: ' + darkThemeBGColor + '; color: ' + darkThemeColor
            : 'background-color: ' + lightThemeBGColor + '; color: ' + lightThemeColor"
        >
          <q-btn
            @click="left = !left"
            dense
            round
            flat
            icon="menu"
            class="q-mr-sm"
          />
          <q-btn
            @click="$q.dark.toggle()"
            flat
            round
            dense
          >
            <img class="img-logo" :src="$q.dark.isActive ? require('../assets/your-trans-5.png') : require('../assets/your-trans-6.png')">
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
            class="q-mr-sm"
          >
          </q-btn>
        </q-toolbar>
        <q-toolbar
          class="q-pa-none"
          :style="$q.dark.isActive ?
            'background-color: ' + darkThemeBGColor + '; color: ' + darkThemeColor
            : 'background-color: ' + lightThemeBGColor + '; color: ' + lightThemeColor"
        >
          <q-space />
          <q-tabs>
            <q-route-tab name="home" label="Início" to="/" />
            <q-route-tab name="about" label="Sobre" to="/about" />
            <q-route-tab name="services" label="Serviços" to="/services" />
            <q-route-tab name="doubts" label="Dúvidas" to="/doubts" />
          </q-tabs>
        </q-toolbar>
      </q-header>
      <q-drawer flat content-class="" bordered :width="250" v-model="left" side="left">
         <q-color no-header default-view="palette" :palette="palette" v-model="lightThemeBGColor" />
         <q-color no-header default-view="palette" :palette="palette" v-model="lightThemeColor" />
         <q-color no-header default-view="palette" :palette="palette" v-model="darkThemeBGColor" />
         <q-color no-header default-view="palette" :palette="palette" v-model="darkThemeColor" />
        <LeftDrawer />
      </q-drawer>
      <q-drawer content-class="" bordered mini :width="65" v-model="right" side="right">
        <RightDrawer />
      </q-drawer>
      <q-page-container>
        <!-- <FadeTransition/> -->
        <div v-if="this.$route.fullPath != '/'"
          class="q-px-xl fit row wrap justify-center items-start content-center"
          :class="this.$route.fullPath.search(/\bios\b/) >= 0 ? '' : 'inset-shadow '"
        >
          <div
            class="q-pt-xs col-auto text-center">
            <q-tabs dense
              class="" no-caps>
              <q-tab
                icon="mdi-web"
                label="Web"
                @click="dynamicRoute('')"
              />
              <q-tab
                icon="mdi-apple-ios"
                label="iPhone"
                @click="dynamicRoute('/ios')"
              />
              <q-tab
                icon="mdi-google-play"
                label="Android" @click="dynamicRoute('/android')"
              />
              <q-tab
                icon="mdi-apple"
                label="Mac"
                @click="dynamicRoute('/mac')"
              />
              <q-tab
                icon="mdi-microsoft"
                label="Windows"
                @click="dynamicRoute('/windows')"
              />
            </q-tabs>
          </div>
        </div>
      <div v-else
        class="q-pa-xl fit row wrap justify-center items-start content-center"
        :class="this.$route.fullPath.search(/\bios\b/) >= 0 ? '' : 'inset-shadow '"
      >
        <div class="col-auto text-center">
          <img class="img-logo" :src="require('../assets/your-trans-6.png')">
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
       <!-- <FadeTransition mode="out-in"> -->
         <!-- <div transition-show="jump-down"
  transition-hide="jump-up"> -->
<transition name="fade" mode="out-in">
      <router-view />
</transition>
         <!-- </div> -->

       <!-- </FadeTransition> -->
      <whatsapp/>
      </q-page-container>
      <q-footer
        container
        style="height: 250px"
        :style="$q.dark.isActive ?
          'background-color: ' + lightThemeBGColor + '; color: ' + lightThemeColor :
          'background-color: ' + darkThemeBGColor + '; color: ' + darkThemeColor"
      >
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
import whatsapp from '../components/whatsapp/Dynamicwhatsapp'
// import FadeTransition from './FadeTransition.vue'

export default {
  components: {
    LeftDrawer,
    RightDrawer,
    whatsapp
    // FadeTransition
  },
  data () {
    return {
      left: false,
      right: false,
      showWallE: true,
      darkThemeBGColor: '#242424FF',
      darkThemeColor: '#FFFFFFFF',
      lightThemeBGColor: '#FFFFFFFF',
      lightThemeColor: '#242424FF',
      palette: ['#FFFFFFFF', '#F2C037FF', '#21BA45FF', '#26A69AFF', '#31CCECFF', '#1976D2FF', '#e600e2ff', '#512fa9ff', '#aa0000ff', '#242424ff']
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
  },
  computed: {
    returnStyle: {
      get () {
        if (this.setStyle === false) {
          return { height: '96vh' }
        } else {
          return { height: '96vh' }
        }
      }
    }
  }
}
</script>

<style>
</style>
