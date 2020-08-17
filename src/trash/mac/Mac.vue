<template>
  <div>
    <div :class="maximize ? '' : 'bg-blue-grey-7 q-pa-md'">
    <q-bar dense outline="false" class="text-white q-electron-drag" style="background-color: #512fa9; border-top-left-radius: 5px; border-top-right-radius: 5px; border-bottom-left-radius: 0px;
        border-bottom-right-radius: 0px;">
      <q-btn dense rounded flat size="5px" color="grey-10" icon="mdi-close" class="q-mx-xs" style="background-color: #e60000;" @click="closeApp" />
      <q-btn dense rounded flat size="5px" color="grey-10" icon="mdi-minus" class="q-mx-xs" style="background-color: #e6b800;" @click="minimize" />
      <q-btn dense rounded flat size="5px" color="grey-10" icon="mdi-menu-swap" class="q-mx-xs rotate45" style="background-color: #2eb82e;" @click="maximize = !maximize" />
      <div class="cursor-pointer gt-md">File</div>
      <div class="cursor-pointer gt-md">Edit</div>
      <div class="cursor-pointer gt-md">View</div>
      <div class="cursor-pointer gt-md">Window</div>
      <div class="cursor-pointer gt-md">Help</div>
      <q-space />
      <q-btn dense flat icon="airplay" class="gt-xs" />
      <q-btn dense flat icon="battery_charging_full" />
      <q-btn dense flat icon="wifi" />
      <div>9:41</div>
      <q-btn dense flat icon="search" />
      <q-btn dense flat icon="list" />
    </q-bar>
    <q-layout view="hHh LpR lfr" container class="shadow-4" :style="maximize ? 'height: 100vh;' : 'height: 90vh;'" style="border-top-left-radius: 0px; border-top-right-radius: 0px;
              border-bottom-left-radius: 5px; border-bottom-right-radius: 5px;">
      <!-- :style="style"  -->
      <q-header reveal class="text-white shadow-4">
        <!-- <q-header elevated> -->
        <q-toolbar class="q-px-xl q-pb-xl q-pt-xl row">
          <!-- @click="$q.dark.toggle()" -->
          <q-btn class="bg-deep-purple-8" style="border-top-left-radius: 5px; border-top-right-radius: 5px; border-bottom-left-radius: 5px;
            border-bottom-right-radius: 5px;" padding="sm md" push @click="$q.dark.toggle()">
          <img class="img-logo" :src="require('../assets/your-trans-5.png')">
        </q-btn>
        <q-space />
        <q-tabs narrow-indicator :breakpoint="0" no-caps>
          <div class="q-pl-sm"></div>
          <q-btn
            push
            label="Início"
            class="navigation-btn bg-deep-purple-8"
            v-if="$q.screen.gt.sm" name="home"
            to="/mac"
          />
            <div class="q-pl-sm"></div>
          <q-btn
            push
            label="Sobre"
            class="navigation-btn bg-deep-purple-8"
            v-if="$q.screen.gt.sm" name="about"
            to="/mac/about" />
          <div class="q-pl-sm"></div>
          <q-btn

               push
        label="Serviços"
        class="navigation-btn bg-deep-purple-8"
        v-if="$q.screen.gt.sm" name="services"
        to="/mac/services" />
      <div class="q-pl-sm"></div>
      <q-btn
        push
        label="Dúvidas"
        class="navigation-btn bg-deep-purple-8"
        v-if="$q.screen.gt.sm" name="doubts"
        to="/mac/doubts" />
      <q-btn-dropdown class="bg-deep-purple-8 q-py-xs q-px-none" :content-style="{ backgroundColor: '#ff000000' }"
        style="border-top-left-radius: 5px; border-top-right-radius: 5px; border-bottom-left-radius: 5px; border-bottom-right-radius: 5px;"
        size="md"
          push no-caps v-if="$q.screen.lt.md" auto-close dropdown-icon="mdi-menu-down" :loading="loading" label="Pages">
        <q-list class="q-pa-none q-ma-none fit column wrap justify-center">
          <q-item
          class="q-pt-xs q-pb-none q-px-none" clickable to="/mac">
            <q-btn size="12px"
              push style="width:100%; border-top-left-radius: 5px; border-top-right-radius: 5px;
              border-bottom-left-radius: 5px; border-bottom-right-radius: 5px;" class="bg-deep-purple-8 text-white" label="Home" />
            </q-item>

            <q-item
            class="q-pt-xs q-pb-none q-px-none" clickable to="/mac/services" >
              <q-btn size="12px"
                push style="width:100%; border-top-left-radius: 5px; border-top-right-radius: 5px;
                border-bottom-left-radius: 5px; border-bottom-right-radius: 5px;" class="bg-deep-purple-8 text-white" label="Serviços" />
            </q-item>

            <q-item
            class="q-pt-xs q-pb-none q-px-none" clickable to="/mac/about" >
              <q-btn size="12px"
                push style="width:100%; border-top-left-radius: 5px; border-top-right-radius: 5px;
                border-bottom-left-radius: 5px; border-bottom-right-radius: 5px;" class="bg-deep-purple-8 text-white" label="Sobre" />
            </q-item>

            <q-item
            class="q-pt-xs q-pb-none q-px-none" clickable to="/mac/doubts" >
              <q-btn size="12px"
                push style="width:100%; border-top-left-radius: 5px; border-top-right-radius: 5px;
                border-bottom-left-radius: 5px; border-bottom-right-radius: 5px;" class="bg-deep-purple-8 text-white" label="Dúvidas" />
            </q-item>
          </q-list>
        </q-btn-dropdown>
      </q-tabs>
    </q-toolbar>
    <!-- <q-separator/> -->
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
    <div v-if="this.$route.fullPath != '/mac'" class="q-px-xl bg-grey-10 fit row wrap justify-center items-start content-center">
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
    <!-- <PagesToolbar/> -->
    <q-page-sticky position="top-left" :offset="[5, 5]">
      <q-btn class="text-white" color="deep-color-8" padding="none" style="background-color: #212121; border-top-left-radius: 3px; border-top-right-radius: 3px;
        border-bottom-left-radius: 3px; border-bottom-right-radius: 3px;" flat @click="left = !left">
        <q-icon name="mdi-menu-open" class="rotate180 q-pa-xs" size="30px" />
      </q-btn>
    </q-page-sticky>
    <q-page-sticky position="top-right" :offset="[5, 5]">
        <q-btn class="text-white" padding="none" style="background-color: #212121; border-top-left-radius: 3px; border-top-right-radius: 3px;
        border-bottom-left-radius: 3px; border-bottom-right-radius: 3px;" flat @click="right = !right">
          <q-icon name="mdi-menu-open" class="q-pa-xs" size="30px" />
        </q-btn>
    </q-page-sticky>
    </q-page-container>
    <q-footer class="bg-grey-10" container style="height: 20px">
      <q-separator/>
        <img class="footer-logo q-pa-xs" :src="require('../assets/yourprojects2.png')">
        <q-space/>
    </q-footer>
  </q-layout>
  <!-- </HomeToolbar> -->
  </div>

  <!-- <q-resize-observer @resize="onResize" /> -->
    </div>
            <!-- </div> -->
          <!-- </div> -->

    <!-- <div class="justify-center">
      Reported:
      <q-badge>width: {{ report.width }}</q-badge>
      <q-badge>height: {{ report.height }}</q-badge>
    </div> -->
    <!-- </div>
  </div> -->
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
      maximize: false,
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
