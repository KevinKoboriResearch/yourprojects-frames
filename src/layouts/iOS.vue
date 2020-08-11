<template>
  <div>
    <q-layout
      view="hHh LpR lFr"
      style="color: #FF4235;"
      :style="$q.dark.isActive ? 'background-color: #212121; color: #FFFFFF' : 'background-color: #FFFFFF; color: #212121'"
    >
    <!-- background-color: #F2F121;  -->
      <q-header
        reveal
        class="transparent"
      >
        <!-- <div
          class="row no-wrap"
          style="background-color: #000000;"
        >
          <q-bar
            class="col-3  q-electron-drag"
            style="background-color: #212121;
              border-top-left-radius: 25px;
              border-top-right-radius: 10px;"
          >
            <q-space />
            <div>
              9:41
            </div>
            <q-space />
          </q-bar>
          <div
            class="col-6"
            style="background-color: #212121;"
          >
            <q-bar
              class="bg-black"
              style="border-bottom-left-radius: 25px;
                border-bottom-right-radius: 25px;"
            >
              <q-space />
              <q-icon style="color: #333333" name="mdi-circle-small" />
              <q-icon style="color: #333333" name="mdi-circle-small" />
              <q-space />
              <q-icon style="color: #333333" name="mdi-drag-horizontal" />
              <q-icon style="color: #333333" name="mdi-drag-horizontal" />
              <q-space />
              <q-icon style="color: #333333" name="mdi-circle-medium" />
              <q-icon style="color: #333333" name="mdi-record" />
              <q-space />
            </q-bar>
          </div>
          <q-bar
            class="col-3  q-electron-drag"
            style="background-color: #212121;
              border-top-left-radius: 10px;
              border-top-right-radius: 25px;"
          >
            <q-space />
            <q-btn dense flat padding="none" icon="mdi-signal" />
            <q-btn dense flat padding="none" icon="wifi" />
            <q-btn dense flat padding="none" icon="battery_charging_full" />
            <q-space />
          </q-bar>
        </div> -->
        <!-- <q-toolbar class="shadow-4 q-px-xl q-pb-xl q-pt-xl row"
          style="background-color: #212121;
            border-bottom-left-radius: 25px;
            border-bottom-right-radius: 25px;">
          <q-btn
            @click="$q.dark.toggle()"
            push
            padding="sm md"
            style="background-color: #4622a2;
              border-top-left-radius: 5px;
              border-top-right-radius: 5px;
              border-bottom-left-radius: 5px;
              border-bottom-right-radius: 5px;"
          >
            <img style="height: 28px;" :src="require('../assets/your-trans-5.png')">
          </q-btn>
          <q-space />
          <q-tabs narrow-indicator :breakpoint="0" no-caps>
            <div class="q-pl-sm" />
            <q-btn
              v-if="$q.screen.gt.sm"
              push
              label="Início"
              to="/ios"
              style="background-color: #4622a2;
                width:100%;
                border-top-left-radius: 5px;
                border-top-right-radius: 5px;
                border-bottom-left-radius: 5px;
                border-bottom-right-radius: 5px;"
            />
            <div class="q-pl-sm" />
            <q-btn
              v-if="$q.screen.gt.sm"
              push
              label="Sobre"
              to="/ios/about"
              style="background-color: #4622a2;
                width:100%;
                border-top-left-radius: 5px;
                border-top-right-radius: 5px;
                border-bottom-left-radius: 5px;
                border-bottom-right-radius: 5px;"
            />
            <div class="q-pl-sm" />
            <q-btn
              v-if="$q.screen.gt.sm"
              push
              label="Serviços"
              to="/ios/services"
              style="background-color: #4622a2;
                width:100%;
                border-top-left-radius: 5px;
                border-top-right-radius: 5px;
                border-bottom-left-radius: 5px;
                border-bottom-right-radius: 5px;"
            />
            <div class="q-pl-sm" />
            <q-btn
              v-if="$q.screen.gt.sm" name="doubts"
              push
              label="Dúvidas"
              to="/ios/doubts"
              style="background-color: #4622a2;
                width:100%;
                border-top-left-radius: 5px;
                border-top-right-radius: 5px;
                border-bottom-left-radius: 5px;
                border-bottom-right-radius: 5px;"
            />
            <q-btn-dropdown
              v-if="$q.screen.lt.md"
              push
              no-caps
              auto-close
              label="Pages"
              size="md"
              dropdown-icon="mdi-menu-down"
              class="q-py-xs q-px-none"
              style="background-color: #4622a2;
                border-top-left-radius: 5px;
                border-top-right-radius: 5px;
                border-bottom-left-radius: 5px;
                border-bottom-right-radius: 5px;"
              :content-style="{ backgroundColor: '#00000000' }"
            >
              <q-list class="q-pa-none q-ma-none fit column wrap justify-center">
                <q-item

                  clickable to="/ios"
                  class="q-pt-xs q-pb-none q-px-none"
                >
                  <q-btn
                    push
                    size="12px"
                    label="Home"
                    class=""
                    style="background-color: #4622a2;
                      width:100%;
                      border-top-left-radius: 5px;
                      border-top-right-radius: 5px;
                      border-bottom-left-radius: 5px;
                      border-bottom-right-radius: 5px;"
                  />
                </q-item>
                <q-item

                  clickable
                  to="/ios/services"
                  class="q-pt-xs q-pb-none q-px-none"
                >
                  <q-btn
                    size="12px"
                    push
                    class="" label="Serviços"
                    style="width:100%;
                    border-top-left-radius: 5px; border-top-right-radius: 5px;
                      border-bottom-left-radius: 5px; border-bottom-right-radius: 5px; background-color: #4622a2;"
                  />
                </q-item>

                    <q-item

                    class="q-pt-xs q-pb-none q-px-none"
                    clickable to="/ios/about" >
                      <q-btn
                      size="12px"
                        push style="width:100%;
                         border-top-left-radius: 5px;
                         border-top-right-radius: 5px;

                        border-bottom-left-radius: 5px;
                         border-bottom-right-radius: 5px; background-color: #4622a2;"
                         class="" label="Sobre" />
                    </q-item>

                    <q-item

                    class="q-pt-xs q-pb-none q-px-none"
                    clickable to="/ios/doubts" >
                      <q-btn
                      size="12px"
                        push style="width:100%;
                         border-top-left-radius: 5px;
                         border-top-right-radius: 5px;

                        border-bottom-left-radius: 5px;
                         border-bottom-right-radius: 5px; background-color: #4622a2;"
                         class="" label="Dúvidas" />
                    </q-item>
                  </q-list>
                </q-btn-dropdown>
              </q-tabs>
            </q-toolbar> -->
            <q-toolbar
              :style="$q.dark.isActive ? 'background-color: #212121; color: #FFFFFF' : 'background-color: #FFFFFF; color: #212121'">
              <q-btn
                @click="left = !left"
                dense
                round
                flat
                icon="menu"
                class="q-mr-sm"
              />
                <!-- :style="$q.dark.isActive ? 'color: #FFFFFF' : 'color: #212121'" -->
              <!-- :style="$q.dark.isActive ? 'background-color: #212121; color: #FFFFFF' : 'background-color: #FFFFFF; color: #212121'" -->
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
                class="q-mr-sm"
              >
                <!-- :style="$q.dark.isActive ? 'color: #FFFFFF' : 'color: #212121'" -->
                <!-- :style="$q.dark.isActive ? '' : ''" -->
              </q-btn>
            </q-toolbar>
            <q-toolbar
              class="q-pa-none"
              :style="$q.dark.isActive ? 'background-color: #212121; color: #FFFFFF' : 'background-color: #FFFFFF; color: #212121'">
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
            <LeftDrawer />
          </q-drawer>
          <q-drawer content-class="" bordered mini :width="65" v-model="right" side="right">
            <RightDrawer />
          </q-drawer>
          <q-page-container>
            <div v-if="this.$route.fullPath != '/ios'"
              class="q-px-xl fit row wrap justify-center items-start content-center">
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
              <q-btn
                @click="left = !left"
                flat
                rounded
                color="white"
                padding="none"
              >
                <!-- style="background-color: #212121" -->
                <q-icon
                  name="mdi-menu-open"
                  size="30px"
                  class="rotate180 q-pa-xs"
                />
              </q-btn>
            </q-page-sticky>
            <q-page-sticky position="top-right" :offset="[10, 10]">
              <q-btn
                @click="right = !right"
                flat
                rounded
                color="white"
                padding="none"
                class=""
              >
                <q-icon
                  name="mdi-menu-open"
                  class="q-pa-xs"
                  size="30px"
                />
              </q-btn>
            </q-page-sticky>
          </q-page-container>
          <!-- <q-toolbar
            style="
              height:76px;
              border-top-left-radius: 40px;
              border-top-right-radius: 40px;
              border-bottom-left-radius: 40px;
              border-bottom-right-radius: 40px;"
          >
            <br>
            <br>
            <br>
            <br>
          </q-toolbar> -->
          <q-footer reveal
            class="q-pa-none q-ma-none  shadow-4"
            style="background-color: #212121;
              margin: 6px;
              border-top-left-radius: 38px;
              border-top-right-radius: 38px;
              border-bottom-left-radius: 38px;
              border-bottom-right-radius: 38px;"
          >
            <q-toolbar
              class="q-pa-none q-ma-none"
              style="border-top-left-radius: 38px;
              border-top-right-radius: 38px;
              border-bottom-left-radius: 38px;
              border-bottom-right-radius: 38px;"
            >
              <q-space/>
              <q-tabs
                indicator-color="white"
                active-color="white"
              >
                <q-route-tab
                  class="q-pa-md"
                  icon="mdi-home-variant"
                  to="/ios"
                />
                <q-route-tab
                  class="q-pa-md"
                  icon="mdi-book"
                  to="/ios/about"
                />
                <q-route-tab
                  class="q-pa-md"
                  icon="mdi-account-supervisor"
                  to="/ios/services"
                />
                <q-route-tab
                  class="q-pa-md"
                  icon="mdi-help-box"
                  to="/ios/doubts"
                />
              </q-tabs>
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

export default {
  components: {
    LeftDrawer,
    RightDrawer,
    whatsapp
  },
  data () {
    return {
      left: false,
      right: false
    }
  },
  methods: {
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
