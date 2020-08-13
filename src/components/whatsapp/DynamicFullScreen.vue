
<template>
  <div>
    <q-page-sticky position="top-right" :offset="fabPos">
      <!-- <q-btn
        @click="$q.fullscreen.toggle()"
        v-touch-pan.prevent.mouse="moveFab"
        glossy
        :disable="draggingFab"
        class="shadow-0 text-white" padding="none" style="background-color:#212121; border-top-left-radius: 50px; border-top-right-radius: 50px;
        border-bottom-left-radius: 0px; border-bottom-right-radius: 50px;"
      >
        <q-icon color="grey-10" :name="$q.fullscreen.isActive ? 'fullscreen_exit' : 'fullscreen'"/>
      </q-btn> -->
      <q-btn
            @click="$q.fullscreen.toggle()"
            v-touch-pan.prevent.mouse="moveFab"
            flat
            :disable="draggingFab"
            padding="none" style="border-top-left-radius: 0px; border-top-right-radius: 0px;
            border-bottom-left-radius: 0px; border-bottom-right-radius: 0px;"
            :style="'backgroud-color: ' + $q.dark.isActive ? 'white' : 'black'"
          >
            <q-icon :color="$q.dark.isActive ? 'white' : 'black'" :name="$q.fullscreen.isActive ? 'fullscreen_exit' : 'fullscreen'"/>
          </q-btn>
    </q-page-sticky>
    <!-- <q-dialog v-model="dialog" persistent :position="position">
      <q-card class="bg-teal-9" style="min-width: 310px; min-height: 200px; background-color: #cdf5c9ff;
        border-top-left-radius: 7px; border-top-right-radius: 7px; border-bottom-left-radius: 0px; border-bottom-right-radius: 0px;">
        <q-card-section class="row q-pa-none bg-teal-9">
          <div @click="openInNewWindow()" class="q-px-md q-py-xs">
            <div class="text-subtitle1 text-white text-weight-bold">Your Projects</div>
            <div class="text-white">+55 61 99342-4369</div>
          </div>
          <q-space />
          <div class="q-py-sm q-px-sm">
            <q-btn padding="none" icon="mdi-close" flat color="brown-1" size="md" class="q-pa-none" v-close-popup />
          </div>
        </q-card-section>
        <q-card-section class="row q-pb-xs bg-brown-2">
          <q-space />
          <div style="background-color: #cdf5c9ff;border-top-left-radius: 10px; border-top-right-radius: 0px;
            border-bottom-left-radius: 10px; border-bottom-right-radius: 10px;"
            :class="'q-px-sm q-py-xs text-black ' + shadowElevation" @click="openInNewWindow()" @mouseover="shadow = true" @mouseleave="shadow = false">Olá!
            <q-icon loading name="mdi-check-all" color="light-blue-5" size="20px" class="q-pa-none q-pl-xs q-pr-none"/>
          </div>
        </q-card-section>
        <q-card-section class="row q-pb-xs q-pt-xs bg-brown-2">
          <div style="background-color: #FFFFFF;border-top-left-radius: 0px; border-top-right-radius: 10px;
            border-bottom-left-radius: 10px; border-bottom-right-radius: 10px;"
            :class="'q-px-sm q-py-xs text-black ' + shadowElevation2" @click="openInNewWindow()" @mouseover="shadow2 = true" @mouseleave="shadow2 = false">Oi, Seja Bem vindo ao Your Projects!
          </div>
          <q-space />
        </q-card-section>
        <q-card-section class="row q-pb-xs q-pt-sm bg-brown-2">
          <q-space />
          <div style="background-color: #cdf5c9ff;border-top-left-radius: 10px; border-top-right-radius: 0px;
            border-bottom-left-radius: 10px; border-bottom-right-radius: 10px;"
            :class="'q-px-sm q-py-xs text-black ' + shadowElevation" @click="openInNewWindow()" @mouseover="shadow = true" @mouseleave="shadow = false">Tenho interesse em uma aplicação.
            <q-icon name="mdi-check-all" color="light-blue-5" size="20px" class="q-pa-none q-pl-xs q-pr-none"/>
          </div>
        </q-card-section>
        <q-card-section class="row q-pb-xs q-pt-sm bg-brown-2">
          <div style="background-color: #FFFFFF;border-top-left-radius: 0px; border-top-right-radius: 10px;
          border-bottom-left-radius: 10px; border-bottom-right-radius: 10px;"
            :class="'q-px-sm q-py-xs text-black ' + shadowElevation2" @click="openInNewWindow()" @mouseover="shadow2 = true" @mouseleave="shadow2 = false">Como posso ajuda-lo?
          </div>
          <q-space />
        </q-card-section>
        <q-card-section class="row q-pa-none bg-brown-2">
          <div class="bg-brown-2">
            <q-input @mouseover="shadow = true" @mouseleave="shadow = false" rounded class="q-py-sm q-pl-sm q-pr-xs" style="min-width: 286px;" dense v-model="text" standout="bg-teal-9 text-white" placeholder="Escreva algo...">
              <template v-slot:append>
                <q-icon name="mdi-close-circle" color="brown-1" size="xs" class="cursor-pointer" @click="text = ''" />
              </template>
            </q-input>
          </div>
          <q-space />
          <div class="q-py-xs q-pr-sm">
              <q-btn round flat icon="mdi-send" color="teal-9" size="10px" class="q-pa-sm" @click="openInNewWindow()" v-close-popup />
          </div>
        </q-card-section>
      </q-card>
    </q-dialog> -->
  </div>
</template>

<script>
export default {
  data: () => ({
    fab: false,
    fabPos: [12, 12],
    draggingFab: false
  }),
  methods: {
    moveFab (ev) {
      this.draggingFab = ev.isFirst !== true && ev.isFinal !== true

      this.fabPos = [
        this.fabPos[0] - ev.delta.x,
        this.fabPos[1] - ev.delta.y
      ]
    }
  }
}
</script>
