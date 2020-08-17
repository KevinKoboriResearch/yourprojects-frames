<template>
<div>
  <!-- <q-btn
    :v-for="btn in pageNum"
    :class="{active:index == btn + 2}"
    @click="moveTo(btn+2)">page {{btn+2}}</q-btn>
  <q-btn type="button" @click="showPage()">add page</q-btn>

  <div class="page-2 page" :v-for="page in pageNum">
    <h2 class="part-2" v-animate="{value: 'bounceInRight'}">page {{page}}</h2>
  </div> -->
  <div class="fullpage-container bg-black">
  <div class="fullpage-wp bg-deep-purple-9 text-center" v-fullpage="opts" ref="example">
    <div class="page-1 page q-pa-xl">oi1<br>oi2<br>oi3<br>oi4<br>
    <div class="q-pa-xl">oi5<br>oi6<br>oi7<br>oi8<br>
    <h1>3d animation using pure CSS3<small>Movie Posters Example</small></h1>
          <p class="part-1" v-animate="{value: 'bounceInLeft', delay: 0}">fullpage-vue</p>
      <p class="part-1" v-animate="{value: 'bounceInRight', delay: 600}">fullpage-vue</p>
      <p class="part-1" v-animate="{value: 'zoomInDown', delay: 1200}">fullpage-vue</p>
    </div>
      <!-- <p class="part-1">1-vue</p> -->
<!-- <div class="bg-green q-pa-md text-justify row wrap justify-center items-center content-center" v-animate="{value: 'bounceInLeft'}">
      <div class="bg-green q-pa-md col-xs-12 col-sm-6 col-md-4" style="max-width:415px"> -->
          <!-- <q-card>
            <img :src="require('../../assets/astronauta.gif')">

            <q-card-section>
              <div class="text-overline text-orange-9">Android & iOS</div>
              <div class="text-h6">Dispositivos Mobile</div>
              <div class="text-subtitle2">por Kevin Kobori</div>
            </q-card-section>

            <q-card-section class="q-pt-none">
              Projeto 100% compatível com dispositivos mobile. Uma vez feito a lógica do código utilizando Javascript, Html e CSS com a ajuda da Framework VueJS
              é possível exporta-lo tanto para dispositivos que utilizam Android quanto iOS. O aplicativo pode ser instalado tanto localmente(sem a necessidade
              de publicação do app em alguma store) quanto direto da Play Store ou da Apple Store. Ótimo para aplicativos de administração empresarial ou de fácil
              visualização de dados como: blogs, cursos online, petshops, sites estáticos de propaganda e Leads(captação de email).
            </q-card-section>

            <q-card-section class="q-pt-none">
              <strong>Ex: Smartphones e Tablets / iPhones e iPads.</strong>
            </q-card-section>
            <br>
            <q-separator inset />

            <q-card-section align="right">
              <q-btn outline>Saiba Mais</q-btn>
            </q-card-section>
          </q-card> -->
        <!-- </div> -->
        <q-btn @click="moveNext">next</q-btn>
<!-- </div> -->
    </div>
    <div class="page-2 page">
      <!-- <p class="part-2">2-vue</p> -->
      <div class="transparent q-pa-md text-justify row wrap justify-center items-start content-start" v-animate="{value: 'bounceInRight'}">
      <div class="bg-blue q-pa-md col-xs-12 col-sm-6 col-md-4" style="max-width:415px">
          <!-- <q-card>
            <img :src="require('../../assets/astronauta.gif')">

            <q-card-section>
              <div class="text-overline text-orange-9">Android & iOS</div>
              <div class="text-h6">Dispositivos Mobile</div>
              <div class="text-subtitle2">por Kevin Kobori</div>
            </q-card-section>

            <q-card-section class="q-pt-none">
              Projeto 100% compatível com dispositivos mobile. Uma vez feito a lógica do código utilizando Javascript, Html e CSS com a ajuda da Framework VueJS
              é possível exporta-lo tanto para dispositivos que utilizam Android quanto iOS. O aplicativo pode ser instalado tanto localmente(sem a necessidade
              de publicação do app em alguma store) quanto direto da Play Store ou da Apple Store. Ótimo para aplicativos de administração empresarial ou de fácil
              visualização de dados como: blogs, cursos online, petshops, sites estáticos de propaganda e Leads(captação de email).
            </q-card-section>

            <q-card-section class="q-pt-none">
              <strong>Ex: Smartphones e Tablets / iPhones e iPads.</strong>
            </q-card-section>
            <br>
            <q-separator inset />

            <q-card-section align="right">
              <q-btn outline>Saiba Mais</q-btn>
            </q-card-section>
          </q-card> -->
        </div>
        <q-btn @click="moveNext">next</q-btn>
</div>
    </div>
    <div class="page-3 page">
      <div class="transparent q-pa-md text-justify row wrap justify-center items-start content-start" v-animate="{value: 'bounceInLeft', delay: 0}">
      <div class="bg-red q-pa-md col-xs-12 col-sm-6 col-md-4" style="max-width:415px">
          <!-- <q-card>
            <img :src="require('../../assets/astronauta.gif')">

            <q-card-section>
              <div class="text-overline text-orange-9">Android & iOS</div>
              <div class="text-h6">Dispositivos Mobile</div>
              <div class="text-subtitle2">por Kevin Kobori</div>
            </q-card-section>

            <q-card-section class="q-pt-none">
              Projeto 100% compatível com dispositivos mobile. Uma vez feito a lógica do código utilizando Javascript, Html e CSS com a ajuda da Framework VueJS
              é possível exporta-lo tanto para dispositivos que utilizam Android quanto iOS. O aplicativo pode ser instalado tanto localmente(sem a necessidade
              de publicação do app em alguma store) quanto direto da Play Store ou da Apple Store. Ótimo para aplicativos de administração empresarial ou de fácil
              visualização de dados como: blogs, cursos online, petshops, sites estáticos de propaganda e Leads(captação de email).
            </q-card-section>

            <q-card-section class="q-pt-none">
              <strong>Ex: Smartphones e Tablets / iPhones e iPads.</strong>
            </q-card-section>
            <br>
            <q-separator inset />

            <q-card-section align="right">
              <q-btn outline>Saiba Mais</q-btn>
            </q-card-section>
          </q-card> -->
        </div>
        <q-btn @click="moveNext">next</q-btn>
</div>

      <p class="part-3" v-animate="{value: 'bounceInLeft', delay: 0}">fullpage-vue</p>
      <p class="part-3" v-animate="{value: 'bounceInRight', delay: 600}">fullpage-vue</p>
      <p class="part-3" v-animate="{value: 'zoomInDown', delay: 1200}">fullpage-vue</p>
    </div>
  </div>
  <!-- <q-btn @click="moveNext">next</q-btn> -->
</div>
</div>
</template>

<script>
export default {
  data () {
    return {
      pageNum: 2,
      opts: {
        start: 0,
        dir: 'v',
        duration: 500,
        beforeChange: function (currentSlideEl, currenIndex, nextIndex) {
        },
        afterChange: function (currentSlideEl, currenIndex) {
        }
      }
    }
  },
  methods: {
    moveNext () {
      this.$refs.example.$fullpage.moveNext() // Move to the next page
    },
    showPage () {
      this.pageNum++
      this.$refs.fullpage.$fullpage.$update()
    }
  }
}
</script>

<style>
.fullpage-container {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
}
</style>
