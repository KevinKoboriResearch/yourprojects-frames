<template>
  <div
  >
    <!-- tabindex="-1"
    @keydown.meta.187.capture.prevent.stop @keydown.meta.107.capture.prevent.stop
    @keydown.meta.189.capture.prevent.stop @keydown.meta.109.capture.prevent.stop
    @keydown.ctrl.187.capture.prevent.stop @keydown.ctrl.107.capture.prevent.stop
    @keydown.ctrl.189.capture.prevent.stop @keydown.ctrl.109.capture.prevent.stop -->
    <!-- @keyup.enter="keyhandler()" -->
<!-- v-on:keyup.13="keyboardEvent" -->
<!-- <br><br><br><br><br><br> -->
<!-- <keyboard-events><input @keydown="keyboardEvent()" /></keyboard-events> -->
<!-- <input v-on:keyup.13="keyboardEvent"> -->
<!-- @keydown.shift.56.capture.prevent.stop="keyhandler()" -->
  <!-- {{tabVal}} -->
    <q-layout
      view="lHr LpR lfr"
      :style="$q.dark.isActive ? 'background-image: linear-gradient(to bottom right, black, #512fa9); color: ' + darkThemeColor
        : 'background-image: linear-gradient(to bottom right, #512fa9, white); color: ' + lightThemeColor"
    >
      <q-header
        class="transparent"
        reveal
      >
      <!-- <input/> -->
      <!-- <input
        @keydown.meta.187.capture.prevent.stop="keyhandler()" @keydown.meta.107.capture.prevent.stop="keyhandler()"
        @keydown.meta.189.capture.prevent.stop="keyhandler()" @keydown.meta.109.capture.prevent.stop="keyhandler()"
        @keydown.ctrl.187.capture.prevent.stop="keyhandler()" @keydown.ctrl.107.capture.prevent.stop="keyhandler()"
        @keydown.ctrl.189.capture.prevent.stop="keyhandler()" @keydown.ctrl.109.capture.prevent.stop="keyhandler()"
      /> -->
      <!-- <input @keydown.ctrl.187.prevent.stop="keyhandler()"
      @keydown.ctrl.107.prevent.stop="keyhandler()"
      @keydown.91.187.prevent.stop="keyhandler()"
      @keydown.91.107.prevent.stop="keyhandler()"/> -->
        <!-- <input @keydown="keyhandler()" /> -->
      <!-- </input> -->
      <!-- <img :src="require('../assets/your-trans-11.png')" @click="toggleZoomScreen()"> -->
      <!-- <img @click="toggleZoomScreen()" class="img-logo" :src="$q.dark.isActive ? require('../assets/your-trans-11.png') : require('../assets/your-trans-10.png')"> -->
        <div class="row no-wrap">
          <q-btn
            @click="left = !left"
            dense
            flat
            :color="$q.dark.isActive ? 'white': 'black'"
            icon="menu"
            class="q-pa-none q-ma-sm"
          />
          <q-space/>
          <div class="justify-center">
            <q-tabs class="row justify-center" no-caps
            style="border-top-left-radius: 0px;
              border-top-right-radius: 0px;
              border-bottom-left-radius: 5px;
              border-bottom-right-radius: 5px;"
            :style="$q.dark.isActive ?
              'background-color: ' + darkThemeBGColor + '; color: ' + darkThemeColor
              : 'background-color: ' + lightThemeBGColor + '; color: ' + lightThemeColor"
            >
              <div @click="tab = 'home'" class="col q-pa-none">
                <q-route-tab label="Início" to="/"/>
              </div>
              <div @click="tab = 'about'" class="col q-pa-none">
                <q-route-tab label="Sobre" to="/about"/>
              </div>
                <q-btn @click="mainArea == false ? (toggleZoomScreen(), mainArea = !mainArea) : tab = 'yourprojects', toggleZoomScreen()" size="18.5px" flat
                class="col q-pa-none"
                style="border-top-left-radius: 0px;
                  border-top-right-radius: 0px;
                  border-bottom-left-radius: 0px;
                  border-bottom-right-radius: 0px;"
                >
                <img class="img-logo" :src="$q.dark.isActive ? require('../assets/your-trans-11.png') : require('../assets/your-trans-10.png')">
              </q-btn>
              <div @click="tab = 'services'" class="col q-pa-none">
                <q-route-tab label="Servicos" to="/services"/>
              </div>
              <div @click="tab = 'doubts'" class="col q-pa-none">
                <q-route-tab label="Dúvidas" to="/doubts"/>
              </div>
            </q-tabs>
          </div>
          <q-space/>
           <q-btn
            @click="right = !right"
            dense
            flat
            :color="$q.dark.isActive ? 'white': 'black'"
            icon="menu"
            class="q-pa-none q-ma-sm"
          />
            </div>
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
        <transition name="bounce">
          <div v-if="mainArea">
            <div
              class="row wrap text-center justify-center items-start content-center"
            >
              <div class="fit row wrap justify-center items-start">
                <q-tab-panels
                  v-model="tab"
                  animated
                  style="background-color: #12121200;"
                >
                  <q-tab-panel style="min-width: 390px;" class="q-pa-md" name="home">
                    <b>Seja bem vindo ao <strong class="text-orange">yourprojects.net</strong></b>
                    <div><b class="text-orange">Fazendo com que o amanhã se torne o hoje!</b></div>
                  </q-tab-panel>
                  <q-tab-panel style="min-width: 390px;" class="q-pa-md" name="about">
                    <b>Criado por <strong class="text-orange">Kevin Kobori</strong></b>
                    <div><b>Facilitando para o <strong class="text-orange">empregado</strong> e o <strong class="text-orange">empregador</strong></b></div>
                  </q-tab-panel>
                  <q-tab-panel style="min-width: 390px;" class="q-pa-sm" name="yourprojects">
                    <q-tabs
                      dense
                      no-caps
                      v-model="ecoSystem"
                    >
                      <q-tab
                        @click="ecoSystem = 'web'"
                        class="col-2"
                        name="web"
                        icon="mdi-web"
                        label="Web"
                      />
                      <q-tab
                        @click="ecoSystem = 'android'"
                        class="col-2"
                        name="android"
                        icon="mdi-android"
                        label="Android"
                      />
                      <q-tab
                        @click="ecoSystem = 'ios'"
                        class="col-2"
                        name="ios"
                        icon="mdi-cellphone-iphone"
                        label="iPhone"
                      />
                      <q-tab
                        @click="ecoSystem = 'windows'"
                        class="col-2"
                        name="windows"
                        icon="mdi-microsoft"
                        label="Windows"
                      />
                      <q-tab
                        @click="ecoSystem = 'mac'"
                        class="col-2"
                        name="mac"
                        icon="mdi-apple"
                        label="Mac"
                      />
                    </q-tabs>
                  </q-tab-panel>
                  <q-tab-panel style="min-width: 390px;" class="q-pa-md" name="services">
                    <b>Responsáveis pelo desenvolvimento do <strong class="text-orange">Seu APP/Site</strong></b>
                    <div><b class="text-orange">...É um desenvolvedor Web?</b><b> Insira o seu portifólio <strong><a href="" class="text-orange">Aqui!</a></strong></b></div>
                  </q-tab-panel>
                  <q-tab-panel style="min-width: 390px;" class="q-pa-md" name="doubts">
                    <b>Do </b><b>design </b><b>a configuração dos servidores de <strong class="text-orange">sua Aplicação</strong></b>
                    <div><b>Trabalhamos com <strong class="text-orange">Frontend, Backend, Banco de Dados...</strong></b></div>
                  </q-tab-panel>
                </q-tab-panels>
              </div>
            </div>
            <q-tab-panels
              v-model="ecoSystem"
              animated
              style="background-color: #12121200;"
            >
              <q-tab-panel
                class="q-pa-none"
                name="web"
              >
                <div id="web-preview" class="platform-web mat-only">
                  <br>
                  <div class="row">
                    <div class="col-1" />
                    <div class="col-10">
                      <q-bar dense>
                        <img class="img-mini-logo" :src="$q.dark.isActive ? require('../assets/your-trans-11.png') : require('../assets/your-trans-10.png')">
                        <q-space />
                        <q-btn dense flat icon="minimize" @click="mainArea = !mainArea" />
                        <q-btn @click="$q.fullscreen.isActive ? '' : $q.fullscreen.toggle(), dialog = true" dense flat icon="crop_square" />
                        <q-btn dense flat icon="close" @click="mainArea = !mainArea" />
                      </q-bar>
                      <div class="q-pa-xs">
                        <q-input dense disable outlined color="deep-purple-8" v-model="frameWebSite" label-slot clearable>
                          <template v-slot:prepend>
                            <q-icon size="xs" name="mdi-lock" />
                          </template>
                          <template v-slot:label>
                            <strong class="text-deep-orange">Your Projects</strong>
                            <strong> always with you</strong>
                          </template>
                        </q-input>
                        <q-dialog
                          v-model="dialog"
                          persistent
                          :maximized="maximizedToggle"
                          transition-show="slide-up"
                          transition-hide="slide-down"
                        >
                          <div class="bg-deep-purple-9">
                            <q-bar dense>
                              <q-space />
                              <q-btn dense flat icon="minimize" v-close-popup>
                                <q-tooltip v-if="maximizedToggle" content-class="bg-white text-primary">Minimize</q-tooltip>
                              </q-btn>
                              <q-btn dense flat icon="crop_square" :disable="maximizedToggle">
                              </q-btn>
                              <q-btn @click="$q.fullscreen.isActive ? $q.fullscreen.toggle() : '', mainArea = !mainArea" dense flat icon="close" v-close-popup>
                                <q-tooltip content-class="bg-white text-primary">Close</q-tooltip>
                              </q-btn>
                            </q-bar>
                            <div id="web-fullscreen-preview" class="platform-web mat-only">
                            <iframe id="web-fullscreen-iframe" frameborder="0" :src="'http://localhost:8080/#' + this.$route.fullPath"/>
                            </div>
                          </div>
                        </q-dialog>
                      </div>
                    </div>
                    <div class="col-1" />
                  </div>
                  <iframe id="web-iframe" frameborder="0" :src="'http://localhost:8080/#' + this.$route.fullPath"/>
                </div>
              </q-tab-panel>
              <q-tab-panel class="q-pa-none" name="android">
                <div id="android-preview" class="platform-android mat-only">
                  <iframe id="android-iframe" frameborder="0" :src="'http://localhost:8080/#/android' + this.$route.fullPath"/>
                </div>
              </q-tab-panel>

              <q-tab-panel class="q-pa-none" name="ios">
                <div id="ios-preview" class="platform-ios mat-only">
                  <iframe id="ios-iframe" frameborder="0" :src="'http://localhost:8080/#/ios' + this.$route.fullPath"/>
                </div>
              </q-tab-panel>

              <q-tab-panel class="q-pa-none" name="windows">
                <div id="windows-preview" class="platform-windows mat-only">
                  <iframe id="windows-iframe" frameborder="0" :src="'http://localhost:8080/#/windows' + this.$route.fullPath" />
                </div>
              </q-tab-panel>
              <q-tab-panel class="q-pa-none" name="mac">
                <!-- <div class="transparent q-pa-md text-justify row wrap justify-center items-start content-start"> -->
                  <!-- <div class="q-pa-md col-xs-12 col-sm-12 col-md-12"> -->
                    <div id="mac-preview" class="platform-mac mat-only">
                      <iframe id="mac-iframe" frameborder="0" :src="'http://localhost:8080/#/mac' + this.$route.fullPath"/>
                    </div>
                  <!-- </div> -->
                <!-- </div> -->
              </q-tab-panel>
            </q-tab-panels>
          </div>
        </transition>
        <div v-if="mainArea == false">
          <div v-if="tab == 'home'">
            <transition name="fade">
              <router-view />
            </transition>
          </div>
          <div v-else-if="tab == 'about'">
            <transition
              name="custom-classes-transition"
              enter-active-class="animated tada"
              leave-active-class="animated bounceOutRight"
            >
              <router-view />
            </transition>
          </div>
          <div v-else-if="tab == 'services'">
            <transition name="slide-fade">
              <router-view />
            </transition>
          </div>
          <div v-else>
            <transition name="bounce">
              <router-view />
            </transition>
          </div>
          <!-- <div v-else>
            <transition
              v-on:before-enter="beforeEnter"
              v-on:enter="enter"
              v-on:leave="leave"
              v-bind:css="false"
            >
              <router-view />
            </transition>
          </div> -->
        </div>
        <whatsapp />
        <DynamicThemeChange />
        <DynamicFullScreen />
          <!-- v-if="mainArea" -->
        <q-page-sticky
          position="top-left" :offset="fabPos">
          <q-btn
            @click="mainArea = !mainArea, toggleZoomScreen()"
            v-touch-pan.prevent.mouse="moveFab"
            flat
            :disable="draggingFab"
            padding="none" style="border-top-left-radius: 0px; border-top-right-radius: 0px;
            border-bottom-left-radius: 0px; border-bottom-right-radius: 0px;"
            :style="'backgroud-color: ' + $q.dark.isActive ? 'white' : 'black'"
          >
            <q-icon :color="$q.dark.isActive ? 'white' : 'black'" :name="mainArea ? 'close' : 'mdi-tablet-cellphone'"/>
          </q-btn>
        </q-page-sticky>
          <q-page-sticky
          position="top-left" :offset="[12, 60]">
          <q-btn
            @click="customColors = !customColors"
            v-touch-pan.prevent.mouse="moveFab"
            flat
            :disable="draggingFab"
            padding="none" style="border-top-left-radius: 0px; border-top-right-radius: 0px;
            border-bottom-left-radius: 0px; border-bottom-right-radius: 0px;"
            :style="'backgroud-color: ' + $q.dark.isActive ? 'white' : 'black'"
          >
            <q-icon :color="$q.dark.isActive ? 'white' : 'black'" :name="mainArea ? 'mdi-water' : 'mdi-tablet-cellphone'"/>
          </q-btn>
        </q-page-sticky>
      </q-page-container>
      <q-footer
        v-if="!mainArea"
        container
        elevated
        style="height: 250px"
        :style="$q.dark.isActive ?
          'background-color: ' + darkThemeBGColor + '; color: ' + darkThemeColor :
          'background-color: ' + lightThemeBGColor + '; color: ' + lightThemeColor"
      >
        <q-toolbar class="q-pa-lg">
          <img class="footer-logo" :src="$q.dark.isActive ? require('../assets/your-trans-5.png') : require('../assets/your-trans-9.png')">
          <q-space/>
        </q-toolbar>
      </q-footer>
    </q-layout>
  </div>
  <!-- </keyboard-events>? -->
</template>

<script>
import LeftDrawer from '../components/drawers/LeftDrawer'
import RightDrawer from '../components/drawers/RightDrawer'
import whatsapp from '../components/whatsapp/Dynamicwhatsapp'
import DynamicThemeChange from '../components/whatsapp/DynamicThemeChange'
import DynamicFullScreen from '../components/whatsapp/DynamicFullScreen'
// import keyboardEvents from '../components/keyboardEvents'

export default {
  components: {
    LeftDrawer,
    RightDrawer,
    whatsapp,
    DynamicThemeChange,
    DynamicFullScreen
    // keyboardEvents
  },
  created () {
    // document.body.style.zoom = '100%'
  //   var elFrame = $('#ios-preview')[0] //pegando o elemento
  //   $(elFrame.contentWindow).resize(function() {
  //       $(window).trigger('zoom')
  //   })

  //   $(window).on('zoom', function() {
  //       console.log('zoom', window.devicePixelRatio)
  //   })
  // },
  // beforeDestroy () {
    // window.removeEventListener('keyup', this.handler);
  },
  data () {
    return {
      teste: true,
      tabVal: 'yourprojects',
      mainAreaVal: true,
      left: false,
      right: false,
      showWallE: true,
      ecoSystem: 'ios',
      customColors: false,
      frameWebSiteVal: 'http://www.yourprojects.net/#',
      dialog: false,
      maximizedToggle: true,
      darkThemeBGColor: '#242424FF',
      darkThemeColor: '#FFFFFFFF',
      lightThemeBGColor: '#FFFFFFFF',
      lightThemeColor: '#242424FF',
      palette: ['#FFFFFFFF', '#F2C037FF', '#21BA45FF', '#26A69AFF', '#31CCECFF', '#1976D2FF', '#e600e2ff', '#512fa9ff', '#aa0000ff', '#242424ff'],
      ab: false,
      fabPos: [12, 12],
      draggingFab: false
    }
  },
  methods: {
    keyboardEvent (e) {
      if (e.which === 13) {
        this.tabVal = 'oi'
        // event.preventDefault()
        alert('you didn t type +, did you?')
      }
    },
    // keyhandler (event) {
    //   if (event.key === '+') {
    //     // do something
    //     this.tabVal = 'home'
    //     event.preventDefault()
    //   }
    // },
    keyhandler (event) {
      this.tabVal = 'oi'
      alert('you didn t type +, did you?')
    },
    toggleZoomScreen () {
      document.body.style.zoom = '100%'
    },
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
    },
    beforeEnter: function (el) {
      el.style.opacity = 0
      el.style.transformOrigin = 'left'
    },
    enter: function (el, done) {
      Velocity(el, { opacity: 1, fontSize: '1.4em' }, { duration: 300 }) // eslint-disable-line
      Velocity(el, { fontSize: '1em' }, { complete: done }) // eslint-disable-line
    },
    leave: function (el, done) {
      Velocity(el, { translateX: '15px', rotateZ: '50deg' }, { duration: 600 }) // eslint-disable-line
      Velocity(el, { rotateZ: '100deg' }, { loop: 2 }) // eslint-disable-line
      Velocity(el, { // eslint-disable-line
        rotateZ: '45deg',
        translateY: '30px',
        translateX: '30px',
        opacity: 0
      }, { complete: done })
    },
    moveFab (ev) {
      this.draggingFab = ev.isFirst !== true && ev.isFinal !== true

      this.fabPos = [
        this.fabPos[0] - ev.delta.x,
        this.fabPos[1] - ev.delta.y
      ]
    }
  },
  computed: {
    // toggleZoomScreen: {
    //   get () {
    //     return this.tabVal
    //   },
    //   set (val) {
    //     document.body.style.zoom = '59%'
    //   }
    // },
    mainArea: {
      get () {
        return this.mainAreaVal
      },
      set (val) {
        this.mainAreaVal = val
        this.tab = 'yourprojects'
      }
    },
    tab: {
      get () {
        return this.tabVal
      },
      set (val) {
        this.tabVal = val
      }
    },
    frameWebSite: {
      get () {
        if (this.frameWebSiteVal === 'http://www.yourprojects.net/#') {
          return this.frameWebSiteVal + this.$route.fullPath
        } else {
          return this.frameWebSiteVal
        }
      },
      set (val) {
        this.frameWebSiteVal = val
      }
    },
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
