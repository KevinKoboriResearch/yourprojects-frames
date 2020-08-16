
<template>
  <div>
    <q-page-sticky
      position="top-left" :offset="windowWidth <= 470 ? [12, 108] : [40, 60]">
      <q-btn
        @click="open('left')"
        flat
        padding="none" style="border-top-left-radius: 0px; border-top-right-radius: 0px;
        border-bottom-left-radius: 0px; border-bottom-right-radius: 0px;"
        :style="'backgroud-color: ' + $q.dark.isActive ? 'white' : 'black'"
      >
        <q-icon :color="$q.dark.isActive ? 'white' : 'black'" name="mdi-water"/>
      </q-btn>
    </q-page-sticky>
    <q-dialog v-model="dialog" :position="position">
      <q-card class="bg-teal-9" style="min-width: 310px; min-height: 200px; background-color: #cdf5c9ff;
        border-top-left-radius: 0px; border-top-right-radius: 5px; border-bottom-left-radius: 0px; border-bottom-right-radius: 5px;">
        <q-card-section class="row q-pa-none bg-teal-9">
          <q-color no-header default-view="palette" :palette="palette" v-model="lightThemeBGColor" />
          <q-color no-header default-view="palette" :palette="palette" v-model="lightThemeColor" />
          <q-color no-header default-view="palette" :palette="palette" v-model="darkThemeBGColor" />
          <q-color no-header default-view="palette" :palette="palette" v-model="darkThemeColor" />
        </q-card-section>
      </q-card>
    </q-dialog>
  </div>
</template>

<script>
export default {
  data: () => ({
    hints: true,
    dialog: false,
    position: 'top',
    shadowVal: false,
    shadowElevation: 'shadow-1',
    shadowVal2: false,
    shadowElevation2: 'shadow-1',
    palette: ['#FFFFFFFF', '#F2C037FF', '#21BA45FF', '#26A69AFF', '#31CCECFF', '#1976D2FF', '#e600e2ff', '#512fa9ff', '#aa0000ff', '#242424ff']
  }),
  methods: {
    open (position) {
      this.position = position
      this.dialog = true
    }
  },
  computed: {
    shadow: {
      get () {
        return this.shadowVal
      },
      set (val) {
        this.shadowVal = val
        if (val === true) {
          this.shadowElevation = 'shadow-4'
        } else {
          this.shadowElevation = 'shadow-1'
        }
      }
    },
    shadow2: {
      get () {
        return this.shadowVal2
      },
      set (val) {
        this.shadowVal2 = val
        if (val === true) {
          this.shadowElevation2 = 'shadow-4'
        } else {
          this.shadowElevation2 = 'shadow-1'
        }
      }
    }
  }
}
</script>
