<template>
     <div>
        <template>
            <div class="">
                <div class="button-group">
                    <button type="button" class="disabled-btn" @click="setDisabled()">Disabled move</button>
                    <button type="button" :class="{active:index ==0}" @click="moveTo(0)">first page</button>
                    <button type="button" :class="{active:index ==1}" @click="moveTo(1)">Second page</button>
                    <button type="button" :class="{active:index ==2}" @click="moveTo(2)">Third page</button>
                    <!-- <button type="button" v-for="btn in pageNum" :class="{active:index == btn + 2}" @click="moveTo(btn+2)">page {{btn+2}}</button> -->
                    <button type="button" @click="showPage()">add page</button>
                </div>
                <div class="fullpage-vertical">
                    <div class="" v-fullpage="opts" ref="fullpage">
                    <div class="page-1 page">
                        <h1 class="part-1" v-animate="{value: 'bounceInLeft'}">vue-fullpage.js</h1>
                        <h3 class="" v-animate="{value: 'bounceInLeft'}">A sigle-page scroll plugin based on vue@2.x,support for mobile and PC .</h3>
                        <div>
                            <p class="part-1" v-animate="{value: 'bounceInRight'}">vue-fullpage</p>
                        </div>
                    </div>
                    <div class="page-2 page">
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
                            </div>
                            <!-- <div class="fullpage-pagination">
                                <div class="fullpage-pagination-bullet"
                                    v-for="(i,index) in [0,1]"
                                    :class="{'fullpage-pagination-bullet__active':active2==index}"></div>
                            </div> -->
                        </div>
                    </div>
                    <div class="page-3 page">
                        <h2 class="part-3" v-animate="{value: 'bounceInLeft'}">Working On Tablets</h2>
                        <h3 class="" v-animate="{value: 'bounceIn'}">Designed to fit different screen sizes as well as tablet and mobile devices. </h3>
                        <p class="part-3" v-animate="{value: 'bounceInLeft',}">vue-fullpage</p>
                        <p class="part-3" v-animate="{value: 'bounceInRight', delay: 300}">vue-fullpage</p>
                        <p class="part-3" v-animate="{value: 'bounceInDown', delay: 600}">vue-fullpage</p>
                        <p class="part-3" v-animate="{value: 'zoomInDown', delay: 900}">vue-fullpage</p>
                    </div>
                    <!-- <div class="page-2 page" v-for="page in pageNum">
                        <h2 class="part-2" v-animate="{value: 'bounceInRight'}">page {{page}}</h2>
                    </div> -->
                </div>
                <!-- <div class="fullpage-pagination">
                    <div class="fullpage-pagination-bullet"
                        v-for="(i,indx) in [0,1,2]"
                        :class="{'fullpage-pagination-bullet__active':index==indx}"></div>
                </div> -->
                </div>
            </div>
        </template>
    </div>
</template>

<script>
export default {
  data () {
    var that = this
    return {
      index: 0,
      pageNum: 0,
      disabled: false,
      opts: {
        start: 0,
        dir: 'v',
        loop: false,
        duration: 300,
        beforeChange (ele, current, next) {
          console.log('before', current, next)
          that.index = next
        },
        afterChange (ele, current) {
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
      },
      active2: 0
    }
  },
  methods: {
    moveTo (index) {
      this.$refs.fullpage.$fullpage.moveTo(index, true, true)
    },
    showPage () {
      this.pageNum++
      this.$refs.fullpage.$fullpage.$update()
    },
    setDisabled () {
      this.disabled = !this.disabled
      this.$refs.fullpage.$fullpage.setDisabled(this.disabled)
    }
  }
}
</script>

<style>
* {
    -webkit-overflow-scrolling: touch;
}
.fullpage-container {
    position: relative;
    width: 100vw;
    height: 100vh;
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
}

    body {
        margin: 0;
    }

    .page {
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
        background-color: rgb(75, 191, 195);
    }

    .page-3 {
        padding-top: 100px;
        background: #aabbcc;
    }
    .page-4{
        padding-top:200px;
        background-color: palevioletred;
    }
    .page-5{
        padding-top:200px;
        background-color: blueviolet;
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
    .fullpage-horizontal,
    .fullpage-vertical{
        position: absolute;
        width:100%;
        height: 100%;

    }

    .fullpage-pagination-bullet{
        margin:0 6px;
        display: block;
        cursor: pointer;
        width: 8px;
        height: 8px;
        display: inline-block;
        border-radius: 100%;
        background: #000;
        opacity: .2;
    }

    .fullpage-pagination-bullet__active{
        background: #1bbc9b;
        opacity: 1;
    }

    .fullpage-horizontal >.fullpage-pagination{
        position: absolute;
        bottom: 20px;
        left: 50%;
        transform: translate(-50%,0);
    }

     .fullpage-vertical > .fullpage-pagination{
        position: fixed;
        right: 20px;
        top: 50%;
        transform: translate(0,-50%);
        display: flex;
        flex-flow: column;
    }

    .fullpage-vertical > .fullpage-pagination > .fullpage-pagination-bullet{
        margin:6px 0;
    }

    .fullpage-vertical > .fullpage-pagination > .fullpage-pagination-bullet__active{
        background: #4D7CFE;
    }

    .button-group button.active {
        background: rgba(0, 0, 0, .5);
        color: #fff;
    }
    button.disabled-btn{
        background: red;
            color: #fff;
    }
</style>
