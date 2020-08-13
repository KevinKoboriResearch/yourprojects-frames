<template>
  <div id="q-app">
    <router-view />
  </div>
</template>
<script>
export default {
  name: 'App'
}
</script>

<style>
body::-webkit-scrollbar {
  width: 0px;
}

.q-card {
  border-radius: 0px;
}

.img-mini-logo {
  height: 15px;
}

.img-logo {
  height: 30px;
}

.img-bg {
  height: 98vh;
}

.footer-logo {
  height: 60px;
}

.rotate180 {
  transform: rotate(180deg);
}

.containerSizeTransition {
  transition: width .3s, height .3s;
}
/*
#web-preview {
  text-align: center;
  width: 100vw;
  height: 81vh;
  margin: -20px auto 0;
}

#web-preview iframe {
  margin-top: 0px;
  width: 83.3vw;
  height: 69vh;
}

#web-fullscreen-preview {
  text-align: center;
  width: 100vw;
  height: 97.5vh;
  background-size: 100vw 97.5vh;
}

#web-fullscreen-preview iframe {
  margin-top: 0px;
  width: 100vw;
  height: 97.5vh;
}

#android-preview {
  text-align: center;
  width: 100vw;
  height: 84vh;
  background: url('./assets/frames/android.png') center top no-repeat;
  background-size: 340px;
  margin: 0 auto 0;
}

#android-preview iframe {
  margin-top: 12px;
  width: 318px;
  height: 618px;
  border-top-left-radius: 20px;
  border-top-right-radius: 20px;
  border-bottom-left-radius: 6px;
  border-bottom-right-radius: 6px;
}

#ios-preview {
  text-align: center;
  width: 98vw;
  height: 84vh;
  background: url('./assets/frames/ios.png') center top no-repeat;
  background-size: 340px;
  margin: -4px auto 0;
}

#ios-preview iframe {
  margin-top: 23px;
  width: 294px;
  height: 635px;
  border-top-left-radius: 30px;
  border-top-right-radius: 30px;
  border-bottom-left-radius: 30px;
  border-bottom-right-radius: 30px;
}

#windows-preview {
  text-align: center;
  width: 93vw;
  height: 85.4vh;
  background: url('./assets/frames/surfacebook-black.png') center 0px no-repeat;
  background-size: 72vw;
  margin: 0 auto 0;
}

#windows-preview iframe {
  margin-top: 2vw;
  width: 54vw;
  height: 37vw;
} */

#web-preview {
  text-align: center;
  width: 100vw;
  height: 81vh;
  margin: -20px auto 0;
}

#web-preview iframe {
  margin-top: 0px;
  width: 83.3vw;
  height: 69vh;
}

#web-fullscreen-preview {
  text-align: center;
  width: 100vw;
  height: 97.5vh;
  background-size: 100vw 97.5vh;
}

#web-fullscreen-preview iframe {
  margin-top: 0px;
  width: 100vw;
  height: 97.5vh;
}

#android-preview {
  text-align: center;
  width: 100vw;
  height: 680px;
  background: url('./assets/frames/android.png') center top no-repeat;
  background-size: 340px;
  margin: 0 auto 0;
}

#android-preview iframe {
  margin-top: 12px;
  width: 318px;
  height: 618px;
  border-top-left-radius: 20px;
  border-top-right-radius: 20px;
  border-bottom-left-radius: 6px;
  border-bottom-right-radius: 6px;
}

#ios-preview {
  text-align: center;
  width: 98vw;
  height: 678px;
  background: url('./assets/frames/ios.png') center top no-repeat;
  background-size: 340px;
  margin: -4px auto 0;
}

#ios-preview iframe {
  margin-top: 23px;
  width: 294px;
  height: 635px;
  border-top-left-radius: 30px;
  border-top-right-radius: 30px;
  border-bottom-left-radius: 30px;
  border-bottom-right-radius: 30px;
}

#windows-preview {
  text-align: center;
  width: 93vw;
  height: 860px;
  background: url('./assets/frames/surfacebook-black.png') center top no-repeat;
  background-size: 720px;
  margin: 0 auto 0;
}

#windows-preview iframe {
  margin-top: 2vw;
  width: 54vw;
  height: 37vw;
}

#mac-preview {
  text-align: center;
  width: 93vw;
  height: 840px;
  background: url('./assets/frames/imac-black.png') center top no-repeat;
  background-size: 63vw;
  margin: 0 auto 0;
  /* text-align: center;
  width: 93vw;
  height: 668px;
  background: url('./assets/frames/ipad-black.png') center top no-repeat;
  background-size: 54vw;
  margin: 0 auto 0; */
}

#mac-preview iframe {
  margin-top: 2.5vw;
  width: 58vw;
  height: 32.5vw;
  /* margin-top: 3.2vw;
  width: 49.5vw;
  height: 36.9vw;
  border-top-left-radius: 25px;
  border-top-right-radius: 25px;
  border-bottom-left-radius: 25px;
  border-bottom-right-radius: 25px; */
}

.slide-fade-enter-active {
  transition: all .3s ease;
}
.slide-fade-leave-active {
  transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}
.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateX(10px);
  opacity: 0;
}

.bounce-enter-active {
  animation: bounce-in .5s;
}
.bounce-leave-active {
  animation: bounce-in .5s reverse;
}
@keyframes bounce-in {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(1.5);
  }
  100% {
    transform: scale(1);
  }
}

/* .bounce-enter-active, .bounce-leave-active {
  transition: opacity .5s;
}
.bounce-enter, .bounce-leave-to{
  opacity: 0;
} */

.fade-enter-active, .fade-enter{
    -webkit-animation: moveFromRight .5s both ease;
    animation: moveFromRight .5s both ease;
  }
  .fade-leave-to, .fade-leave-active {
    -webkit-animation: moveToLeft 1s both ease;
    animation: moveToLeft 1s both ease;
  }
  .layout-padding {
    padding: 1em 4em;
  }
  @media screen and (max-width: 600px){
    .layout-padding {
      padding: 1.5em .5em;
    }
  }
  .menu-enter-active, .scale-enter{
    -webkit-animation: moveFromLeftFade .9s ease both;
    animation: moveFromLeftFade .9s ease both;
  }
  .menu-leave-to, .scale-leave-active {
    -webkit-animation: moveToLeft .9s ease both;
    animation: moveToLeft .9s ease both;
  }

  @-webkit-keyframes moveFromLeftFade {
    from { opacity: 0.3; -webkit-transform: translateX(-100%); }
  }
  @keyframes moveFromLeftFade {
    from { opacity: 0.3; -webkit-transform: translateX(-100%); transform: translateX(-100%); }
  }
  @-webkit-keyframes moveToRight {
    from { }
    to { -webkit-transform: translateX(100%); }
  }

  @keyframes cartOut {
    from {
      transform: translate(0px, 0px);
    }
    to {
      transform: translate(1200px, 0px);
      animation-timing-function: ease-out;
    }

  }
  @-webkit-keyframes moveToLeft {
    from { }
    to { opacity: .5; -webkit-transform: translateX(-100%); }
  }
  @keyframes moveToLeft {
    from { }
    to { opacity: .5; -webkit-transform: translateX(-100%); transform: translateX(-100%); }
  }

  @-webkit-keyframes moveFromRight {
    from { opacity: .7; -webkit-transform: translateX(100%); }
  }
  @keyframes moveFromRight {
    from {opacity: .7; -webkit-transform: translateX(100%); transform: translateX(100%); }
  }
/*
  .drawer-closer .item-content {
    margin-left: 50px !important;
  }
  .drawer-content .list-label {
    line-height: 45px;
  }
  .drawer-content .item {
    height: 45px;
  }
  .router-link-active .item-primary{
    color: #027be3;
  }
  .q-picker-textfield .q-picker-textfield-label{
    color: inherit !important;
  }
  .label-success .q-picker-textfield-label {
    color: #4caf50 !important;
  }
  .label-error .q-picker-textfield-label {
    color: #f44336 !important;
  }
  select {
    -webkit-appearance: none;
    -moz-appearance: none;
    text-indent: 1px;
    text-overflow: '';
  }
  .label-success .q-picker-textfield:after, .label-error .q-picker-textfield:after{
    content: "" !important;
  }

  canvas {
    width: 270px !important;
  }
  @media only screen and (min-width: 601px){
    .adv-form-one .timeline-badge {
      right: auto !important;
      left: auto !important;
    }
    .adv-form-one .timeline-content {
      margin-left: 3.9rem;
    }
    .adv-form-one .timeline-item {
      width: 100% !important;
    }
    .adv-form-one .timeline-title {
      text-align: inherit !important;
      margin-left: 3.9rem;
    }
    .timeline:before {
      left: 1.6rem;
    }
  }
  .adv-form-one .timeline-content .group .primary {
    display: none !important;
  }
  .underline {
    text-decoration: underline;
  } */
</style>
