<template>
<div>
    <q-layout view="hHh LpR lFr" class="transparent">
      <q-header reveal class="text-white bg-light-blue-9">
        <div class="row no-wrap">
          <q-bar class="bg-light-blue-9 col-5 text-white q-electron-drag">
            <q-space />
            <div>9:41</div>
            <q-space />
          </q-bar>
        <div class="col-2 bg-light-blue-9">
            <q-bar class="bg-black"  style="border-top-left-radius: 0px; border-top-right-radius: 0px;
        border-bottom-left-radius: 30px; border-bottom-right-radius: 30px;">
        <!-- <q-space/>
        <q-icon class="text-grey-9" name="mdi-circle-small"></q-icon>
        <q-icon class="text-grey-9" name="mdi-circle-small"></q-icon>
        <q-space/> -->
        <!-- <q-icon class="text-grey-9" name="mdi-drag-horizontal"></q-icon>
        <q-icon class="text-grey-9" name="mdi-drag-horizontal"></q-icon> -->
        <q-space/>
        <!-- <q-icon class="text-grey-9" name="mdi-circle-medium"></q-icon> -->
        <!-- <q-icon class="text-grey-9" name="mdi-record"></q-icon> -->
        <q-icon class="text-grey-10 q-pb-sm" size="30px" name="mdi-camera-iris"></q-icon>
        <q-space/>
            </q-bar>
        </div>
    <q-bar class="col-5 bg-light-blue-9 text-white q-electron-drag">
      <q-space />
      <q-btn dense flat padding="none" icon="mdi-signal" />
      <q-btn dense flat padding="none" icon="wifi" />
      <q-btn dense flat padding="none" icon="battery_charging_full" />
      <q-space />
    </q-bar>
        </div>
        <q-toolbar class="shadow-4 bg-light-blue-9 q-px-xl q-pb-xl q-pt-xl row" style="background-color: #512fa9;
        border-top-left-radius: 0px; border-top-right-radius: 0px; border-bottom-left-radius: 0px; border-bottom-right-radius: 0px;">
          <q-btn class="bg-light-blue-10" style="border-top-left-radius: 0px; border-top-right-radius: 0px; border-bottom-left-radius: 0px;
            border-bottom-right-radius: 0px;" padding="sm md" push @click="$q.dark.toggle()">
          <img style="height: 28px;" :src="require('../assets/your-trans-5.png')">
        </q-btn>
        <q-space />
        <q-tabs narrow-indicator :breakpoint="0" no-caps>
          <div class="q-pl-sm"></div>
          <q-btn
            push
            label="Início"
            class="navigation-btn bg-light-blue-10"
            v-if="$q.screen.gt.sm" name="home"
            to="/android"
          />
            <div class="q-pl-sm"></div>
          <q-btn
            push
            label="Sobre"
            class="navigation-btn bg-light-blue-10"
            v-if="$q.screen.gt.sm" name="about"
            to="/android/about" />
          <div class="q-pl-sm"></div>
          <q-btn

               push
        label="Serviços"
        class="navigation-btn bg-light-blue-10"
        v-if="$q.screen.gt.sm" name="services"
        to="/android/services" />
      <div class="q-pl-sm"></div>
      <q-btn
        push
        label="Dúvidas"
        class="navigation-btn bg-light-blue-10"
        v-if="$q.screen.gt.sm" name="doubts"
        to="/android/doubts" />
      <q-btn-dropdown class="bg-light-blue-10 q-py-xs q-px-none" :content-style="{ backgroundColor: '#ff000000' }"
        style="border-top-left-radius: 0px; border-top-right-radius: 0px; border-bottom-left-radius: 0px; border-bottom-right-radius: 0px;"
        size="md"
          push no-caps v-if="$q.screen.lt.md" auto-close dropdown-icon="mdi-menu-down" :loading="loading" label="Pages">
        <q-list class="q-pa-none q-ma-none fit column wrap justify-center">
          <q-item
          class="q-pt-xs q-pb-none q-px-none" clickable to="/android">
            <q-btn size="12px"
              push style="width:100%; border-top-left-radius: 0px; border-top-right-radius: 0px;
              border-bottom-left-radius: 0px; border-bottom-right-radius: 0px;" class="bg-light-blue-10 text-white" label="Home" />
            </q-item>

            <q-item
            class="q-pt-xs q-pb-none q-px-none" clickable to="/android/services" >
              <q-btn size="12px"
                push style="width:100%; border-top-left-radius: 0px; border-top-right-radius: 0px;
                border-bottom-left-radius: 0px; border-bottom-right-radius: 0px;" class="bg-light-blue-10 text-white" label="Serviços" />
            </q-item>

            <q-item
            class="q-pt-xs q-pb-none q-px-none" clickable to="/android/about" >
              <q-btn size="12px"
                push style="width:100%; border-top-left-radius: 0px; border-top-right-radius: 0px;
                border-bottom-left-radius: 0px; border-bottom-right-radius: 0px;" class="bg-light-blue-10 text-white" label="Sobre" />
            </q-item>

            <q-item
            class="q-pt-xs q-pb-none q-px-none" clickable to="/android/doubts" >
              <q-btn size="12px"
                push style="width:100%; border-top-left-radius: 0px; border-top-right-radius: 0px;
                border-bottom-left-radius: 0px; border-bottom-right-radius: 0px;" class="bg-light-blue-10 text-white" label="Dúvidas" />
            </q-item>
          </q-list>
        </q-btn-dropdown>
      </q-tabs>
    </q-toolbar>
  </q-header>
  <q-drawer flat content-class="bg-white" bordered :width="250" v-model="left" side="left">
    <LeftDrawer
    />
  </q-drawer>
  <q-drawer content-class="bg-white" bordered mini :width="65" v-model="right" side="right">
    <RightDrawer
    />
  </q-drawer>
  <q-page-container>
    <div v-if="this.$route.fullPath != '/android'" class="q-px-xl bg-grey-10 fit row wrap justify-center items-start content-center">
      <div class="q-pt-xs col-auto text-center text-white">
        <q-tabs dense class="text-white" no-caps>
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
      class="q-pa-xl bg-grey-10 fit row wrap justify-center items-start content-center"
      :class="this.$route.fullPath.search(/\bios\b/) >= 0 ? '' : 'inset-shadow '"
    >
      <div class="col-auto text-center text-white">
        <img class="img-logo" :src="require('../assets/your-trans-4.png')">
          <div class="text-subtitle1"><strong>Criando um </strong><strong class="per-word-strong">único</strong>
            <strong> produto, presente em todas as </strong><strong class="per-word-strong">plataformas.</strong></div>
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
    <q-page-sticky position="top-left" :offset="[10, 10]">
      <q-btn class="text-white" color="deep-color-8" padding="none" style="background-color: #212121; border-top-left-radius: 15px; border-top-right-radius: 15px;
        border-bottom-left-radius: 15px; border-bottom-right-radius: 15px;" flat @click="left = !left">
        <q-icon name="mdi-menu-open" class="rotate180 q-pa-xs" size="30px" />
      </q-btn>
    </q-page-sticky>
    <q-page-sticky position="top-right" :offset="[10, 10]">
      <q-btn class="text-white" padding="none" style="background-color: #212121; border-top-left-radius: 15px; border-top-right-radius: 15px;
      border-bottom-left-radius: 15px; border-bottom-right-radius: 15px;" flat @click="right = !right">
        <q-icon name="mdi-menu-open" class="q-pa-xs" size="30px" />
      </q-btn>
    </q-page-sticky>
    </q-page-container>
    <q-footer reveal class="transparent" style="height: 80px">
      <q-toolbar class="bg-light-blue-9 shadow-4 text-white q-pa-none" >
        <q-space/>
        <q-tabs
        indicator-color="white"
        active-color="grey-10">
          <q-route-tab
            class="q-pa-lg"
            icon="mdi-home-variant"
            to="/android"
          />
          <q-route-tab
            class="q-pa-lg"
            icon="mdi-book"
            to="/android/about"
          />
          <q-route-tab
            class="q-pa-lg"
            icon="mdi-account-supervisor"
            to="/android/services"
          />
          <q-route-tab
            class="q-pa-lg"
            icon="mdi-help-box"
            to="/android/doubts"
          />
        </q-tabs>
        <q-space/>
      </q-toolbar>
    </q-footer>
  </q-layout>
    </div>
</template>

<script>
// import HomeToolbar from '../components/toolbars/HomeToolbar'
import LeftDrawer from '../components/drawers/LeftDrawer'
import RightDrawer from '../components/drawers/RightDrawer'
import whatsapp from '../components/whatsapp/Dynamicwhatsapp'
// import PagesToolbar from '../components/toolbars/PagesToolbar'

export default {
  components: {
    LeftDrawer,
    RightDrawer,
    whatsapp
    // HomeToolbar
    // PagesToolbar
  },
  created () {
    window.addEventListener('resize', this.handleResize)
    this.handleResize()
  },
  destroyed () {
    window.removeEventListener('resize', this.handleResize)
  },
  data () {
    return {
      left: false,
      right: false,
      loading: false,
      style: { width: '1300px', height: '750px' },
      styleHeight: { height: '88vh' },
      setStyle: false,
      window: { width: '166vh', height: '88vh' },
      // setStyle
      report: ''
      // routeHomeVal: false
    }
  },
  methods: {
    handleResize () {
      this.window.innerWidth = window.width
      this.window.innerHeight = window.height
    },
    // returnStyle () {
    //   if (this.loading === false) {
    //     return 'height: 96vh'
    //   } else {
    //     return this.style
    //   }
    // },
    dynamicRoute (val) {
      const about = '/about'
      const services = '/services'
      const doubts = '/doubts'
      if (this.$route.fullPath.search(/\babout\b/) >= 0) {
        this.$router.push(val + about)
      } else if (this.$route.fullPath.search(/\bservices\b/) >= 0) {
        this.$router.push(val + services)
      } else if (this.$route.fullPath.search(/\bdoubts\b/) >= 0) {
        this.$router.push(val + doubts)
      } else {
        this.$router.push(val)
      }
    },
    onResize (size) {
      this.report = size
    },
    setRandomSize () {
      this.setStyle = true
      // this.window = {
      //   width: Math.floor(250 + Math.random() * 800) + 'px',
      //   height: Math.floor(400 + Math.random() * 800) + 'px'
      // }
      this.style = {
        width: Math.floor(250 + Math.random() * 800) + 'px',
        height: Math.floor(400 + Math.random() * 800) + 'px'
      }
    },
    setDefaultSize () {
      this.setStyle = false
      // this.style = {
      //   width: '166vh',
      //   height: '88vh'
      // }
    }
    // routeHome (val) {
    //   this.routeHomeVal = val
    // }
  },
  computed: {
    returnStyle: {
      get () {
        if (this.setStyle === false) {
          // this.styleHeight = { height: '96vh' }
          return { height: '96vh' }
        } else {
          // this.styleHeight = { height: '96vh' }
          return { height: '96vh' }
        }
      }
    }
  }
  // whatch: {
  //   routeHome
  // },
  // computed: {
  //   routeHome: {
  //     get () {
  //       return this.routeHomeVal
  //     },
  //     set () {
  //       // this.routeHomeVal = val
  //       // const about = 'about'
  //       // const services = 'services'
  //       // const doubts = 'doubts'
  //       if (!this.$route.fullPath.search(/\babout\b/) && !this.$route.fullPath.search(/\bservices\b/) && !this.$route.fullPath.search(/\bdoubts\b/)) {
  //         this.routeHomeVal = true
  //       } else {
  //         this.routeHomeVal = false
  //       }
  //     }
  //   }
  // }
}
</script>

<style>
</style>
