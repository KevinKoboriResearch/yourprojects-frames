
<template>
  <div>
    <q-page-sticky
      position="top-left" :offset="$store.state.window.windowWidth <= 500 ? [12, 108] : [12, 60]">
      <q-btn
        @click="dialog = !dialog"
        flat
        padding="none" style="border-top-left-radius: 0px; border-top-right-radius: 0px;
        border-bottom-left-radius: 0px; border-bottom-right-radius: 0px;"
        :style="'backgroud-color: ' + $q.dark.isActive ? 'white' : 'black'"
      >
        <q-icon :color="$q.dark.isActive ? 'white' : 'black'" name="mdi-water"/>
      </q-btn>
    </q-page-sticky>
    <q-page-sticky v-if="dialog"
      position="top-left" :offset="$store.state.window.windowWidth <= 500 ? [50, 108] : [50, 60]">
      <q-color no-header default-view="palette" :palette="palette" v-model="themeBGColor"
        style="border-top-left-radius: 0px; border-top-right-radius: 0px;
          border-bottom-left-radius: 0px; border-bottom-right-radius: 0px;" />
        <q-color no-header default-view="palette" :palette="palette" v-model="themeColor"
        style="border-top-left-radius: 0px; border-top-right-radius: 0px;
          border-bottom-left-radius: 0px; border-bottom-right-radius: 0px;"/>
    </q-page-sticky>
  </div>
</template>

<script>
export default {
  data: () => ({
    dialog: false,
    themeBGColorVal: '#242424FF',
    themeColorVal: '#FFFFFFFF',
    palette: ['#FFFFFFFF', '#F2C037FF', '#21BA45FF', '#26A69AFF', '#31CCECFF', '#1976D2FF', '#e600e2ff', '#512fa9ff', '#aa0000ff', '#242424ff']
  }),
  computed: {
    themeBGColor: {
      get () {
        return this.themeBGColorVal
      },
      set (val) {
        this.$store.commit('colors/updateThemeBGColor', val)
        this.themeBGColorVal = val
      }
    },
    themeColor: {
      get () {
        return this.themeColorVal
      },
      set (val) {
        this.$store.commit('colors/updateThemeColor', val)
        this.themeColorVal = val
      }
    }
  }
}
</script>
