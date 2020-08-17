<template>

  <!-- <div
    class="fit transparent text-justify row wrap justify-center items-start"
  > -->
  <div>
    <!-- <div class="transparent q-pa-md text-justify row wrap justify-center items-start content-start"> -->
      <!-- <div class="q-pa-md col-xs-12 col-sm-6 col-md-4" style="max-width:415px"> -->
    <h1>3d animation using pure CSS3<small>Movie Posters Example</small></h1>
      <lu id="movieposters" class="transparent q-pa-md text-justify row wrap justify-center items-start content-start">
          <q-btn @click="crep = !crep">
            oi
          </q-btn>
          <q-card v-if="crep" class="q-pa-md col-xs-12 col-sm-6 col-md-4">
            heey
          </q-card>
        <li :class="crep ? 'row q-pa-md col-xs-12 col-sm-6 col-md-4' : 'row q-pa-md col-xs-12 col-sm-12 col-md-12'">
          <!-- <img v-if="crep" src="../../assets/images/01_iron_man_2.jpg" alt="Iron Man 2" /> -->
        <div class="col-1">oisdsoisdsoisdsoisdsoisdsoisdsoisdsoisdsoisdsoisdsoisdsoisdsoisdsoisdsoisds
          <div id="mac2-preview" class="platform-mac mat-only">
          <iframe id="mac2-iframe" frameborder="0" :src="'http://localhost:8080/#' + this.$route.fullPath"/>
          <!-- <iframe>oi</iframe> -->
        </div>
        </div>
        <div class="col-11">

        <div id="mac2-preview" class="platform-mac mat-only">
          <iframe id="mac2-iframe" frameborder="0" :src="'http://localhost:8080/#' + this.$route.fullPath"/>
          <!-- <iframe>oi</iframe> -->
        </div>
        </div>
        </li>
        <li class="q-pa-md col-xs-12 col-sm-12 col-md-6">
          <!-- <img src="../../assets/images/01_iron_man_2.jpg" alt="Iron Man 2" /> -->
        <div id="mac2-preview" class="platform-mac mat-only">
          <iframe id="mac2-iframe" frameborder="0" :src="'http://localhost:8080/#' + this.$route.fullPath"/>
          <!-- <iframe>oi</iframe> -->
        </div>
        </li>
        <li class="q-pa-md col-xs-12 col-sm-6 col-md-4">
          <img src="../../assets/images/01_iron_man_2.jpg" alt="Iron Man 2" />
          <div class="movieinfo">
            <h3>Iron Man 2</h3>
            <p>With the world now aware of his dual divfe as the armored superhero Iron Man, bildivonaire inventor Tony...</p>
            <a href="http://www.imdb.com/title/tt1228705/" title="Iron Man 2">More info</a>
          </div>
        </li>
                <!-- </div> -->

        <!-- <div class="q-pa-md col-xs-12 col-sm-6 col-md-4" style="max-width:415px"> -->
        <li class="q-pa-md col-xs-12 col-sm-6 col-md-4">
          <img src="../../assets/images/02_the_last_airbender.jpg" alt="The Last Airbender" />
          <div class="movieinfo">
            <h3>The Last Airbender</h3>
            <p>The story follows the adventures of Aang, a young successor to a long divne of Avatars, who must put his...</p>
            <a href="http://www.imdb.com/title/tt0938283/" title="Iron Man 2">More info</a>
          </div>
        </li>
                <!-- </div> -->

        <!-- <div class="q-pa-md col-xs-12 col-sm-6 col-md-4" style="max-width:415px"> -->
        <li class="q-pa-md col-xs-12 col-sm-6 col-md-4">
          <img src="../../assets/images/03_tron_legacy.jpg" alt="Tron Legacy" />
          <div class="movieinfo">
            <h3>Tron Legacy</h3>
            <p>Sam Flynn, the tech-savvy 27-year-old son of Kevin Flynn, looks into his father's disappearance and finds...</p>
            <a href="http://www.imdb.com/title/tt1104001/" title="Tron Legacy">More info</a>
          </div>
        </li>
        <!-- </div> -->
      </lu>
    <!-- </div> -->
    <!-- <h1>3d animation using pure CSS3<small>Movie Posters Example</small></h1>
    <ul id="movieposters">
      <li class="q-pa-md col-xs-12 col-sm-6 col-md-4">
        <img src="../../assets/images/01_iron_man_2.jpg" alt="Iron Man 2" />
        <div class="movieinfo">
          <h3>Iron Man 2</h3>
          <p>With the world now aware of his dual life as the armored superhero Iron Man, billionaire inventor Tony...</p>
          <a href="http://www.imdb.com/title/tt1228705/" title="Iron Man 2">More info</a>
        </div>
      </li>
      <li class="q-pa-md col-xs-12 col-sm-6 col-md-4">
        <img src="../../assets/images/02_the_last_airbender.jpg" alt="The Last Airbender" />
        <div class="movieinfo">
          <h3>The Last Airbender</h3>
          <p>The story follows the adventures of Aang, a young successor to a long line of Avatars, who must put his...</p>
          <a href="http://www.imdb.com/title/tt0938283/" title="Iron Man 2">More info</a>
        </div>
      </li>
      <li class="q-pa-md col-xs-12 col-sm-6 col-md-4">
        <img src="../../assets/images/03_tron_legacy.jpg" alt="Tron Legacy" />
        <div class="movieinfo">
          <h3>Tron Legacy</h3>
          <p>Sam Flynn, the tech-savvy 27-year-old son of Kevin Flynn, looks into his father's disappearance and finds...</p>
          <a href="http://www.imdb.com/title/tt1104001/" title="Tron Legacy">More info</a>
        </div>
      </li>
    </ul> -->
      <!-- </div>
    </div> -->
  <div style="heigth:800px">
  </div>
  </div>
  <!-- </div> -->
</template>

<script>
export default {
  data () {
    return {
      crep: false
    }
  }
}
</script>

<style>
#movieposters li #mac2-preview {
  border:1px solid #7c50ff;
  -webkit-transform: rotateY(15deg);
  -moz-box-shadow:0 3px 10px #888;
  -webkit-box-shadow:0 3px 10px #888;
  -webkit-transition-property: transform;
  -webkit-transition-duration: 1s;
  margin: 0 0 0 20vw;
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
  background: url('../../assets/lol.gif') center center no-repeat;
  background-size: 2000px;
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
