<template>
            <div class="fullpage-container text-center">
              <!-- <div class=" q-pa-xl text-center"> -->
                <!-- <q-btn> -->
                <!-- </q-btn> -->
                <!-- <br><br><br><br><br><br> -->
                  <!-- <div>
                    <q-btn :class="{active:index ==0}" @click="moveTo(0)">first page</q-btn>
                    <q-btn :class="{active:index ==1}" @click="moveTo(1)">Second page</q-btn>
                    <q-btn :class="{active:index ==2}" @click="moveTo(2)">Third page</q-btn>
                  </div> -->
                <div class="fullpage-wp" v-fullpage="opts" ref="fullpage">
                    <div class="page-1 page page-scroll" style="background-image: linear-gradient(purple, purple);">
                        <h1 class="part-1" v-animate="{value: 'bounceInLeft'}">YOUR PROJECTS </h1>
                        <h2 v-animate="{value: 'bounceInLeft'}">scroll in pages</h2>
                        <h3 class="" v-animate="{value: 'bounceInLeft'}">A sigle-page scroll plugin based on vue@2.x,support for mobile and PC .</h3>
                    </div>
                    <div class="page-2 page page-scroll" style="background-image: linear-gradient(grey, grey);">
                        <!-- <h2 class="part-2">Easy to use plugin</h2> -->
                        <div v-animate="{value: 'bounceInRight'}">
                          <div class="transparent q-pa-md text-justify row wrap justify-center items-start content-start" v-animate="{value: 'bounceInLeft'}">
                            <div class="q-pa-md col-xs-12 col-sm-6 col-md-4" style="max-width:415px">
                                <q-card>
                                  <img :src="require('../../assets/astronauta.gif')">

                                  <q-card-section>
                                    <div class="text-overline text-orange-9">Android & iOS</div>
                                    <div class="text-h6">Dispositivos Mobile</div>
                                    <div class="text-subtitle2">por Kevin Kobori</div>
                                  </q-card-section>

                                  <q-card-section class="q-pt-none">

                                  </q-card-section>

                                  <q-card-section class="q-pt-none">
                                    <strong>Ex: Smartphones e Tablets / iPhones e iPads.</strong>
                                  </q-card-section>
                                  <br>
                                  <q-separator inset />

                                  <q-card-section align="right">
                                    <q-btn outline>Saiba Mais</q-btn>
                                  </q-card-section>
                                </q-card>
                              </div>

                              <div class="q-pa-md col-xs-12 col-sm-6 col-md-4" style="max-width:415px">
                                <q-card>
                                  <img src="https://cdn.quasar.dev/img/mountains.jpg">

                                  <q-card-section>
                                    <div class="text-overline text-orange-9">Windows & Mac OSX</div>
                                    <div class="text-h6">Sistemas Operacionais</div>
                                    <div class="text-subtitle2">por Kevin Kobori</div>
                                  </q-card-section>

                                  <q-card-section class="q-pt-none">

                                  </q-card-section>

                                  <q-card-section class="q-pt-none">
                                    <strong>Ex: um botão, um card, uma caixa de texto, utilizados com frequencia durante o desenvolvimento de toda a aplicação.</strong>
                                  </q-card-section>

                                  <q-separator inset />

                                  <q-card-section align="right">
                                    <q-btn outline>Saiba Mais</q-btn>
                                  </q-card-section>
                                </q-card>
                              </div>

                              <div class="q-pa-md col-xs-12 col-sm-6 col-md-4" style="max-width:415px">
                                <q-card>
                                  <img src="https://cdn.quasar.dev/img/mountains.jpg">

                                  <q-card-section>
                                    <div class="text-overline text-orange-9">Chrome, Safari, Firefox...</div>
                                    <div class="text-h6">Navegadores Web</div>
                                    <div class="text-subtitle2">por Kevin Kobori</div>
                                  </q-card-section>

                                  <q-card-section class="q-pt-none">

                                  </q-card-section>

                                  <q-card-section class="q-pt-none">
                                    <strong>Ex: um botão, um card, uma caixa de texto, utilizados com frequencia durante o desenvolvimento de toda a aplicação.</strong>
                                  </q-card-section>

                                  <q-separator inset />

                                  <q-card-section align="right">
                                    <q-btn outline>Saiba Mais</q-btn>
                                  </q-card-section>
                                </q-card>
                              </div>
                              <!-- <div class="q-pa-md col-xs-12 col-sm-6 col-md-4" style="max-width:415px">
                                <q-card>
                                  <img src="https://cdn.quasar.dev/img/mountains.jpg">

                                  <q-card-section>
                                    <div class="text-overline text-orange-9">Design Externo da Página</div>
                                    <div class="text-h6">Layouts</div>
                                    <div class="text-subtitle2">por Kevin Kobori</div>
                                  </q-card-section>

                                  <q-card-section class="q-pt-none">
                                    Componentes permitem você dividir a UI em partes independentes,
                                    reutilizáveis, ou seja, trata cada parte da aplicação como um bloco isolado,
                                    livre de outras dependências externas. Componentes são como funções JavaScript.
                                    Eles aceitam entradas e retornam elementos VueJS que descrevem o que deve aparecer na tela.
                                  </q-card-section>

                                  <q-card-section class="q-pt-none">
                                    <strong>Ex: um botão, um card, uma caixa de texto, utilizados com frequencia durante o desenvolvimento de toda a aplicação.</strong>
                                  </q-card-section>

                                  <q-separator inset />

                                  <q-card-section align="right">
                                    <q-btn outline>Saiba Mais</q-btn>
                                  </q-card-section>
                                </q-card>
                              </div>

                              <div class="q-pa-md col-xs-12 col-sm-6 col-md-4" style="max-width:415px">
                                <q-card>
                                  <img src="https://cdn.quasar.dev/img/mountains.jpg">

                                  <q-card-section>
                                    <div class="text-overline text-orange-9">Design Interno da Página</div>
                                    <div class="text-h6">Componentes</div>
                                    <div class="text-subtitle2">por Kevin Kobori</div>
                                  </q-card-section>

                                  <q-card-section class="q-pt-none">
                                    Componentes permitem você dividir a UI em partes independentes,
                                    reutilizáveis, ou seja, trata cada parte da aplicação como um bloco isolado,
                                    livre de outras dependências externas. Componentes são como funções JavaScript.
                                    Eles aceitam entradas e retornam elementos VueJS que descrevem o que deve aparecer na tela.
                                  </q-card-section>

                                  <q-card-section class="q-pt-none">
                                    <strong>Ex: um botão, um card, uma caixa de texto, utilizados com frequencia durante o desenvolvimento de toda a aplicação.</strong>
                                  </q-card-section>

                                  <q-separator inset />

                                  <q-card-section align="right">
                                    <q-btn outline>Saiba Mais</q-btn>
                                  </q-card-section>
                                </q-card>
                              </div>

                              <div class="q-pa-md col-xs-12 col-sm-6 col-md-4" style="max-width:415px">
                                <q-card>
                                  <img src="https://cdn.quasar.dev/img/mountains.jpg">

                                  <q-card-section>
                                    <div class="text-overline text-orange-9">Material Design Icons</div>
                                    <div class="text-h6">Icones</div>
                                    <div class="text-subtitle2">por Kevin Kobori</div>
                                  </q-card-section>

                                  <q-card-section class="q-pt-none">
                                    Componentes permitem você dividir a UI em partes independentes,
                                    reutilizáveis, ou seja, trata cada parte da aplicação como um bloco isolado,
                                    livre de outras dependências externas. Componentes são como funções JavaScript.
                                    Eles aceitam entradas e retornam elementos VueJS que descrevem o que deve aparecer na tela.
                                  </q-card-section>

                                  <q-card-section class="q-pt-none">
                                    <strong>Ex: um botão, um card, uma caixa de texto, utilizados com frequencia durante o desenvolvimento de toda a aplicação.</strong>
                                  </q-card-section>

                                  <q-separator inset />

                                  <q-card-section align="right">
                                    <q-btn outline>Saiba Mais</q-btn>
                                  </q-card-section>
                                </q-card>
                            </div> -->
                          </div>
                      </div>
                    </div>
                    <div class="page-3 page page-scroll" style="background-image: linear-gradient(black, black);">
                        <!-- <h2 class="" v-animate="{value: 'bounceInTop'}">Working On Tablets</h2>
                        <h3 class="" v-animate="{value: 'bounceInBotton'}">Designed to fit different screen sizes as well as tablet and mobile devices. </h3>
                        <p class="part-3" v-animate="{value: 'bounceInLeft', delay: 0}">vue-fullpage</p>
                        <p class="part-3" v-animate="{value: 'bounceInRight', delay: 300}">vue-fullpage</p>
                        <p class="part-3" v-animate="{value: 'bounceInDown', delay: 600}">vue-fullpage</p>
                        <p class="part-3" v-animate="{value: 'zoomInDown', delay: 900}">vue-fullpage</p> -->
                        <div class="fullpage-horizontal">
                            <div v-fullpage="horizontalOpts" ref="fullpageHorizontal">
                                <div class="page-4 page">
                                    <h2 class="part-2" v-animate="{value: 'bounceInRight'}">Easy to use plugin</h2>
                                    <p v-animate="{value: 'bounceInRight'}">nesting</p>
                                    <p v-animate="{value: 'bounceInRight'}">
                                        horizontal 1
                                    </p>
                                </div>
                                <div class="page-5 page">
                                    <p v-animate="{value: 'bounceInDown'}">horizontal 2</p>
                                </div>
                                 <div class="page-5 page">
                                    <p v-animate="{value: 'bounceInDown'}">horizontal 3</p>
                                </div>
                                 <div class="page-5 page">
                                    <p v-animate="{value: 'bounceInDown'}">horizontal 4</p>
                                </div>
                            </div>
                            <!-- <div class="fullpage-pagination">
                                <div class="fullpage-pagination-bullet"
                                    v-for="(i,index) in [0,1]"
                                    :class="{'fullpage-pagination-bullet__active':active2==index}"></div>
                            </div> -->
                        </div>
                    </div>
                    <!-- <div class="page-2 page" v-for="page in pageNum">
                        <h2 class="part-2" v-animate="{value: 'bounceInRight'}">page {{page}}</h2>
                    </div> -->
                </div>
              <!-- </div> -->
            </div>
</template>

<script>
export default {
//   data () {
//     return {
//       pageNum: 2,
//       crep: false,
//       opts: {
//         start: 0,
//         dir: 'v',
//         duration: 500,
//         beforeChange: function (currentSlideEl, currenIndex, nextIndex) {
//         },
//         afterChange: function (currentSlideEl, currenIndex) {
//         }
//       }
//     }
//   },
//   methods: {
//     moveNext () {
//       this.$refs.example.$fullpage.moveNext() // Move to the next page
//     },
//     showPage () {
//       this.pageNum++
//       this.$refs.fullpage.$fullpage.$update()
//     }
//   }
// }
  data () {
    var that = this
    return {
      index: 0,
      // pageNum: 0,
      opts: {
        start: 0,
        dir: 'v',
        loop: false,
        duration: 100,
        overflow: 'scroll',
        beforeChange: function (elem, current, next) {
          console.log('before', current, next)
        },
        afterChange: function (elem, current) {
          that.index = current
          console.log('after', current)
        }
      },
      horizontalOpts: {
        start: 0,
        dir: 'h',
        loop: false,
        afterChange (ele, current) {
          that.active2 = current
        }
      }
    }
  },
  methods: {
    moveTo: function (index) {
      const $fullpage = this.$refs.fullpage.$fullpage
      if (index < this.index) {
        $fullpage.pageEles[this.index].scrollTo(0, 0)
      } else {
        $fullpage.pageEles[this.index].scrollTo(0, $fullpage.pageEles[this.index].scrollHeight)
      }
      $fullpage.moveTo(index, true)
      this.index = index
    },
    showPage: function () {
      this.pageNum++
      this.$refs.fullpage.$fullpage.$update()
    }
  }
}
</script>

<style>
* {
    -webkit-overflow-scrolling: touch;
}
/* .fullpage-container {
    position: relative;
    width: 100%;
    height: 100%;
    overflow: hidden;
}
.fullpage-wp {
    display: flex;
    width: 100%;
    height: 100%;
    flex-flow: column nowrap;
    justify-content: flex-start;
    align-items: center;
}
.fullpage-wp.anim {
    transform: translate3d(0, 0, 0);
    -webkit-transition: all 500ms ease-out 0s;
    transition: all 500ms ease-out 0s;
}
.fullpage-wp.fullpage-wp-h {
    display: flex;
    flex-flow: row nowrap;
    justify-content: flex-start;
    align-items: center;
}
.page {
    box-sizing: border-box;
    display: block;
    position: relative;
    width: 100%;
    height: 100%;
    flex-shrink: 0;
    overflow: hidden;
}
.animated {
    opacity: 1;
} */

    /* body {
        margin: 0;
        overflow: hidden;
    } */

    .fullpage-container {
        position: absolute;
        /* padding: 0; */
        overflow: hidden;
        margin: 0;
        left: 0;
        top: 0;
        width: 100vw;
        height: 100vh;
    }

    .page-scroll {
        padding-top: 100px;
        background-color: rgb(75, 191, 195);
        overflow-y: scroll;
    }
    .page-scroll::-webkit-scrollbar {
      width: 0px;
    }

    /* .page {
        display: block;
        text-align: center;
        font-size: 26px;
        color: #eee;
    }

    .page-1 {
        padding-top: 100px;
        background: #1bbc9b;
    }

    .page-2 {
        padding-top: 100px;
        background-color: rgb(75, 191, 195);
        overflow-y: scroll;
    }
    .page-2::-webkit-scrollbar {
      width: 0px;
    }
    .page-3 {
        padding-top: 50px;
        background: #aabbcc;
    }

    h3,
    p {
        font-size: 16px;
    }

    .button-group {
        position: absolute;
        top: 30px;
        left: 30px;
        z-index: 9;
    }

    .button-group button {
        display: inline-block;
        margin: 10px;
        color: #000;
        background: #fff;
        background: rgba(255, 255, 255, .5);
        -webkit-border-radius: 10px;
        border-radius: 10px;
        padding: 9px 18px;
        border: none;
        outline: none;
    }

    .button-group button.active {
        background: rgba(0, 0, 0, .5);
        color: #fff;
    } */
</style>
