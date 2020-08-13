<template>
   <div class="img-bg" :style="$q.dark.isActive ? 'background-image: linear-gradient(to bottom right, black, #512fa9);'
          : 'background-image: linear-gradient(to bottom right, white, #512fa9);'">
          <br>
          <div
            class="row wrap justify-center items-start content-center"
          >
            <div class="fit row wrap justify-center items-start">
              <q-tab-panels
                v-model="tab"
                animated
                style="background-color: #12121200;"
              >
                <q-tab-panel class="q-pa-none" name="home" >
                </q-tab-panel>
                <q-tab-panel class="q-pa-none" name="about">
                  <div class="text-h6">Alarms</div>
                  Lorem ipsum dolor sit amet consectetur adipisicing elit.
                </q-tab-panel>
                <q-tab-panel class="q-pa-none" name="yourprojects">
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
                <q-tab-panel class="q-pa-none" name="services">
                  <div class="text-h6">Movies</div>
                  Lorem ipsum dolor sit amet consectetur adipisicing elit.
                </q-tab-panel>
                <q-tab-panel class="q-pa-none" name="doubts">
                  <div class="text-h6">Alarms</div>
                  Lorem ipsum dolor sit amet consectetur adipisicing elit.
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
                    <div class="col-1">
                    </div>
                    <div class="col-10">
                      <q-bar dense>
                        <img class="img-mini-logo" :src="$q.dark.isActive ? require('../../assets/your-trans-11.png') : require('../../assets/your-trans-10.png')">
                        <q-space />
                        <q-btn dense flat icon="minimize" @click="mainArea = !mainArea" />
                        <q-btn @click="$q.fullscreen.isActive ? '' : $q.fullscreen.toggle(), dialog = true" dense flat icon="crop_square" />
                        <q-btn dense flat icon="close" @click="mainArea = !mainArea" />
                      </q-bar>
                      <div class="q-pa-xs">
                        <q-input dense outlined color="deep-purple-8" v-model="frameWebSite" label-slot clearable>
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
                          <q-card class="bg-primary text-white">
                            <q-bar>
                              <q-space />
                              <q-btn dense flat icon="minimize" @click="maximizedToggle = false" :disable="!maximizedToggle">
                                <q-tooltip v-if="maximizedToggle" content-class="bg-white text-primary">Minimize</q-tooltip>
                              </q-btn>
                              <q-btn dense flat icon="crop_square" @click="maximizedToggle = true" :disable="maximizedToggle">
                                <q-tooltip v-if="!maximizedToggle" content-class="bg-white text-primary">Maximize</q-tooltip>
                              </q-btn>
                              <q-btn @click="$q.fullscreen.isActive ? $q.fullscreen.toggle() : ''" dense flat icon="close" v-close-popup>
                                <q-tooltip content-class="bg-white text-primary">Close</q-tooltip>
                              </q-btn>
                            </q-bar>

                            <q-card-section>
                              <div class="text-h6">Alert</div>
                            </q-card-section>

                            <q-card-section class="q-pt-none">
                              Lorem ipsum dolor sit amet consectetur adipisicing elit. Rerum repellendus sit voluptate voluptas eveniet porro. Rerum blanditiis perferendis totam, ea at omnis vel numquam exercitationem aut, natus minima, porro labore.
                            </q-card-section>
                          </q-card>
                        </q-dialog>
                      </div>
                    </div>
                    <div class="col-1">
                    </div>
                  </div>
                  <iframe id="web-iframe" frameborder="0" :src="frameWebSite"/>
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

                <div id="mac-preview" class="platform-mac mat-only">
                  <iframe id="mac-iframe" frameborder="0" :src="'http://localhost:8080/#/mac' + this.$route.fullPath"/>
                </div>
            </q-tab-panel>
          </q-tab-panels>
        </div>
</template>

<script>
export default {
  data () {
    return {
      tab: 'web',
      ecoSystem: 'web',
      frameWebSiteVal: 'http://www.yourprojects.net/#'
    }
  },
  computed: {
    frameWebSite: {
      get () {
        return this.frameWebSiteVal + this.$route.fullPath
      },
      set (val) {
        if (this.frameWebSiteVal.search(/\www.yourprojects.net\b/) >= 0) {
          if (this.frameWebSiteVal.search(/\bhttp\b/) >= 0) {
            this.frameWebSiteVal = val
          } else {
            this.frameWebSiteVal = 'http://' + val
          }
        } else {
          this.frameWebSiteVal = val
        }
      }
    }
  }
}
</script>

<style>

</style>
