<template>
<div>
  <!-- <div class="fullpage-container bg-black"> -->
  <div class="fullpage-wp text-center bg-black" v-fullpage="opts" ref="example">
    <div class="page-1 page q-pa-xl bg-deep-purple-8">
      <p class="part-3" v-animate="{value: 'bounceInLeft', delay: 0}">fullpage-vue</p>
      <p class="part-3" v-animate="{value: 'bounceInRight', delay: 600}">fullpage-vue</p>
      <p class="part-3" v-animate="{value: 'zoomInDown', delay: 1200}">fullpage-vue</p>
       <ul v-animate="{value: 'bounceInRight'}">
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                        </ul>
    </div>
    <div class="page-2 page q-pa-xl bg-deep-purple-7">
      <p class="part-3" v-animate="{value: 'bounceInLeft', delay: 0}">fullpage-vue</p>
      <p class="part-3" v-animate="{value: 'bounceInRight', delay: 600}">fullpage-vue</p>
      <p class="part-3" v-animate="{value: 'zoomInDown', delay: 1200}">fullpage-vue</p>
    </div>
    <div class="page-3 page q-pa-xl bg-deep-purple-6">
      <p class="part-3" v-animate="{value: 'bounceInLeft', delay: 0}">fullpage-vue</p>
      <p class="part-3" v-animate="{value: 'bounceInRight', delay: 600}">fullpage-vue</p>
      <p class="part-3" v-animate="{value: 'zoomInDown', delay: 1200}">fullpage-vue</p>
    </div>
  </div>
  <!-- <q-btn @click="moveNext">next</q-btn> -->
  <!-- </div> -->
</div>
  <!-- <q-btn
    :v-for="btn in pageNum"
    :class="{active:index == btn + 2}"
    @click="moveTo(btn+2)">page {{btn+2}}</q-btn>
  <q-btn type="button" @click="showPage()">add page</q-btn>

  <div class="page-2 page" :v-for="page in pageNum">
    <h2 class="part-2" v-animate="{value: 'bounceInRight'}">page {{page}}</h2>
  </div> -->
  <!-- <div class="fullpage-container bg-black">
  <div class="fullpage-wp text-center bg-black" v-fullpage="opts" ref="example">
    <div class="page-1 page q-pa-xl bg-green">
      <lu id="movieposters" class="transparent q-pa-md text-justify row wrap justify-center items-start content-start">
          <li class="q-pa-md col-xs-12 col-sm-12 col-md-12">
        <div id="mac2-preview" class="platform-mac mat-only">
          <iframe id="mac2-iframe" frameborder="0" :src="'http://localhost:8080/#' + this.$route.fullPath"/>
        </div>
        </li>
      </lu>
    </div>
    <div class="page-2 page q-pa-xl bg-blue">
    </div>
    <div class="page-3 page q-pa-xl bg-red">
      <p class="part-3" v-animate="{value: 'bounceInLeft', delay: 0}">fullpage-vue</p>
      <p class="part-3" v-animate="{value: 'bounceInRight', delay: 600}">fullpage-vue</p>
      <p class="part-3" v-animate="{value: 'zoomInDown', delay: 1200}">fullpage-vue</p>
    </div>
  </div>
  <q-btn @click="moveNext">next</q-btn>
</div>
<div class="fullpage-container">
                <div class="button-group">
                    <button type="button" :class="{active:index ==0}" @click="moveTo(0)">first page</button>
                    <button type="button" :class="{active:index ==1}" @click="moveTo(1)">Second page</button>
                    <button type="button" :class="{active:index ==2}" @click="moveTo(2)">Third page</button>
                </div>
                <div class="fullpage-wp" v-fullpage="opts" ref="fullpage">
                    <div class="page-1 page">
                        <h1 class="part-1" v-animate="{value: 'bounceInLeft'}">vue-fullpage.js </h1>
                        <h2 v-animate="{value: 'bounceInLeft'}">scroll in pages</h2>
                        <h3 class="" v-animate="{value: 'bounceInLeft'}">A sigle-page scroll plugin based on vue@2.x,support for mobile and PC .</h3>
                    </div>
                    <div class="page-2 page">
                        <h2 class="part-2" v-animate="{value: 'bounceInRight'}">Easy to use plugin</h2>
                        <ul v-animate="{value: 'bounceInRight'}">
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                            <li>text</li>
                        </ul>
                    </div>
                    <div class="page-3 page">
                        <h2 class="" v-animate="{value: 'bounceInTop'}">Working On Tablets</h2>
                        <h3 class="" v-animate="{value: 'bounceInBotton'}">Designed to fit different screen sizes as well as tablet and mobile devices. </h3>
                        <p class="part-3" v-animate="{value: 'bounceInLeft', delay: 0}">vue-fullpage</p>
                        <p class="part-3" v-animate="{value: 'bounceInRight', delay: 300}">vue-fullpage</p>
                        <p class="part-3" v-animate="{value: 'bounceInDown', delay: 600}">vue-fullpage</p>
                        <p class="part-3" v-animate="{value: 'zoomInDown', delay: 900}">vue-fullpage</p>
                    </div>
                    <div class="page-2 page" :v-for="page in pageNum">
                        <h2 class="part-2" v-animate="{value: 'bounceInRight'}">page {{page}}</h2>
                    </div>
                </div>
            </div>
</div> -->
</template>

<script>
export default {
  data () {
    return {
      pageNum: 2,
      crep: false,
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
//   data () {
//     var that = this
//     return {
//       index: 0,
//       pageNum: 0,
//       opts: {
//         start: 0,
//         dir: 'v',
//         loop: false,
//         duration: 300,
//         overflow: 'scroll',
//         beforeChange: function (elem, current, next) {
//           console.log('before', current, next)
//         },
//         afterChange: function (elem, current) {
//           that.index = current
//           console.log('after', current)
//         }
//       }
//     }
//   },
//   methods: {
//     moveTo: function (index) {
//       const $fullpage = this.$refs.fullpage.$fullpage
//       /* Fast solution
//       index > this.index scroll to bottom
//       || scroll to top */
//       if (index < this.index) {
//         $fullpage.pageEles[this.index].scrollTo(0, 0)
//       } else {
//         $fullpage.pageEles[this.index].scrollTo(0, $fullpage.pageEles[this.index].scrollHeight)
//       }
//       $fullpage.moveTo(index, true)
//       this.index = index
//     },
//     showPage: function () {
//       this.pageNum++
//       this.$refs.fullpage.$fullpage.$update()
//     }
//   }
// }
</script>

<style>
/* .fullpage-container {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
} */

#movieposters li #mac2-preview {
  /* border:1px solid #7c50ff; */
  -webkit-transform: rotateY(15deg);
  /* -moz-box-shadow:0 3px 10px #888; */
  /* -webkit-box-shadow:0 3px 10px #888; */
  /* -webkit-transition-property: transform; */
  -webkit-transition-duration: 1s;
  margin: 0 0 0 25vw;
}
#movieposters li:hover #mac2-preview {
  -webkit-transform: rotateY(0deg);
  /* margin: 0 auto 0; */
}

#mac2-preview {
  text-align: center;
  /* align-items: center; */
  /* width: 93vw; */

  height: 840px;
  background: url('../../assets/frames/imac-black.png') center center no-repeat;
  background-size: 1500px;
  /* margin: -25px auto 0; */
}

#mac2-preview iframe {
  position: absolute;
  margin: 94px -323px 0;
  width: 644px;
  height: 364px;
}

/* BASIC RESET */
ul,ol,li,h1,h2,h3,h4,h5,h6,pre,form,body,html,p,blockquote,fieldset,input{margin:0; padding:0;}

/* HTML ELEMENTS */
body { background-color:#deddcd; font:14px/21px Arial,Helvetica,sans-serif; }
h1 { font: bold 65px/60px Helvetica, Arial, Sans-serif; text-align: center; color: #eee; text-shadow: 0px 2px 6px #333; }
h1 small{ font-size: 20px; text-transform:uppercase; letter-spacing: 14px; display: block; color: #000; }
h2 a { display: block; text-decoration: none; margin: 0 0 30px 0; font: italic 45px Georgia, Times, Serif;  text-align: center; color: #bfe1f1; text-shadow: 0px 2px 6px #333; }
h2 a:hover { color: #90bcd0; }

/* COMMON CLASSES */
.break {
  clear:both;
}

/* WRAPPER */
#wrapper {
  width:960px;
  margin:40px auto;
}

/* CONTENT */
#content { }
#content .info {
  padding:10px;
}

/* MOVIE POSTERS */
#movieposters {
  justify: center;
  list-style:none;
  margin:0 0;
  height:550px;
}
#movieposters li {
  margin:100px 0;
  display:inline;
  float:left;
  -webkit-perspective: 500;
  -webkit-transform-style: preserve-3d;
  -webkit-transition-property: perspective;
  -webkit-transition-duration: 0.5s;
}

#movieposters li:hover {
  -webkit-perspective: 5000;
}

#movieposters li img {
  border:10px solid #fcfafa;
  -webkit-transform: rotateY(30deg);
  -moz-box-shadow:0 3px 10px #888;
  -webkit-box-shadow:0 3px 10px #888;
  -webkit-transition-property: transform;
  -webkit-transition-duration: 0.5s;
}
#movieposters li:hover img {
  -webkit-transform: rotateY(0deg);
}

.movieinfo {
  border:10px solid #fcfafa;
  padding:20px; width:200px;
  height:180px;
  background-color:#deddcd;
  margin:-195px 0 0 55px;
  position:absolute;
  -moz-box-shadow:0 20px 40px #888;
  -webkit-box-shadow:0 20px 40px #888;
  -webkit-transform: translateZ(30px)
  rotateY(30deg);
  -webkit-transition-property: transform, box-shadow, margin;
  -webkit-transition-duration: 0.5s;
}
#movieposters li:hover .movieinfo {
  -webkit-transform: rotateY(0deg);
  -webkit-box-shadow:0 5px 10px #888;
  margin:-175px 0 0 30px;
}
.movieinfo h3 {
  color:#7a3f3a;
  font-variant: small-caps;
  font-family:Georgia,serif,Times;
  text-align:center;
  padding-bottom:15px;
}
.movieinfo p {
  padding-bottom:15px;
}
.movieinfo a {
  background-color:#7a3f3a;
  padding:5px 10px;
  color:#eee;
  text-decoration:none;
  display:block;
  width:80px;
  text-align:center;
  margin:0 auto;
  -moz-border-radius:5px;
  -webkit-border-radius:5px;
}
.movieinfo a:hover, .movieinfo a:focus {
  background-color:#6a191f;
  color:#fff;
}
</style>
