<template>
    <v-container>
      <div class="scene">
        <div class="box">
          <div class="box__flap box__flap--left"></div>
          <div class="box__flap box__flap--right"></div>
          <div class="box__back">
            <div class="box__back-face"></div>
          </div>
          <div class="card card--1"></div>
          <div class="card card--2"></div>
          <div class="card card--3"></div>
          <div class="card card--4"></div>
          <div class="card card--5"></div>
          <div class="box__front">
            <div class="box__front-face"></div>
          </div>
          <div class="box__left"></div>
          <div class="box__right"></div>  
          <div class="box__bottom"></div>
          <div class="box__lid">
            <div class="box__lid-inner">
              <div class="box__lid-top">
                <div class="box__lid-top-logo"></div>
                <div class="box__lid-top-back"></div>
              </div>
              <div class="box__lid-flap">
                <div class="box__lid-flap-shape">
                  <div class="box__lid-flap-shape-inner"></div>
                  <div class="box__lid-flap-shape-outer"></div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </v-container>
  </template>
  
  <script>
  import gsap from 'gsap'
  export default {
    name: 'BlackjackPage',
    methods: {
      boxIn () {
        let tl = gsap.timeline()
          .set('.scene', { autoAlpha: 1 })
          .fromTo(".box", { rotationY: -540, y: "100vh" }, { duration: 2, rotationY: 0, y: "16vh", ease: "power2" })
          .to(".box__lid", { rotateX:-225, duration: 0.5, ease: "sine.inOut" }, "-=1.4")
          .to(".box__lid-flap", { rotateX: 60, duration: 0.5, ease: "sine.inOut" }, "-=1.2")
          .to(".box__flap--left", { rotateX: "-=135", duration: 0.5, ease: "sine.inOut", transformOrigin: "50% 100%" }, "-=1")
          .to(".box__flap--right", { rotateX: "-=135", duration: 0.5, ease: "sine.inOut", transformOrigin: "50% 100%" }, "-=1") 
        return tl
      },
      rotationAnim () {
        let tl = gsap.timeline({ repeat: -1 })
          .to(".box", { rotateY: 180, ease: "power2.inOut", duration: 0.8 })
          .fromTo(".box__back", { webkitFilter: "brightness(1)", filter: "brightness(1)" }, { duration: 0.8, webkitFilter: "brightness(0.2)", filter: "brightness(0.2)", ease: "power4.inOut" }, 0)
          .fromTo(".box__left", { webkitFilter: "brightness(1)", filter: "brightness(1)" }, { duration: 0.8, webkitFilter: "brightness(0.8)", filter: "brightness(0.8)", ease: "power4.inOut" }, 0)
          .fromTo(".box__lid-top-logo", { webkitFilter: "brightness(1)", filter: "brightness(1)" },{ duration: 0.8, webkitFilter: "brightness(0.85)", filter: "brightness(0.85)", ease: "power2.inOut" }, 0.2)
          .to(".card--1", { keyframes:[{ duration: 0.4, y: "-155%", transformOrigin: "center bottom", ease: "sine" }, { duration: 0.6, rotation: 50, x: "40%", ease: "power2", delay: -0.25}]}, 0.2) // keyframes array
          .to(".card--2", { keyframes:[{ duration: 0.4, y: "-160%", transformOrigin: "center bottom", ease: "sine" }, { duration: 0.6, rotation: 25, x: "20%", ease: "power2", delay: -0.25}]}, 0.2)
          .to(".card--3", { keyframes:[{ duration: 0.4, y: "-160%", transformOrigin: "center bottom", ease: "sine" }, { duration: 0.6, rotation: 0, x: "0%", ease: "power2", delay: -0.25}]}, 0.2)
          .to(".card--4", { keyframes:[{ duration: 0.4, y: "-160%", transformOrigin: "center bottom", ease: "sine" }, { duration: 0.6, rotation: -25, x: "-20%", ease: "power2", delay: -0.25}]}, 0.2)
          .to(".card--5", { keyframes:[{ duration: 0.4, y: "-155%", transformOrigin: "center bottom", ease: "sine" }, { duration: 0.6, rotation: -50, x: "-40%", ease: "power2", delay: -0.25}]}, 0.2)
          .to(".card--1", { keyframes:[{ duration: 0.6, rotation: 0, x: "0%", ease: "power2.in" }, { duration: 0.4, y: "0%", transformOrigin: "center bottom", ease: "sine.in", delay: -0.25 }]}, 1.4)
          .to(".card--2", { keyframes:[{ duration: 0.6, rotation: 0, x: "0%", ease: "power2.in" }, { duration: 0.4, y: "0%", transformOrigin: "center bottom", ease: "sine.in", delay: -0.25 }]}, 1.4)
          .to(".card--3", { keyframes:[{ duration: 0.6, rotation: 0, x: "0%", ease: "power2.in" }, { duration: 0.4, y: "0%", transformOrigin: "center bottom", ease: "sine.in", delay: -0.25 }]}, 1.4)
          .to(".card--4", { keyframes:[{ duration: 0.6, rotation: 0, x: "0%", ease: "power2.in" }, { duration: 0.4, y: "0%", transformOrigin: "center bottom", ease: "sine.in", delay: -0.25 }]}, 1.4)
          .to(".card--5", { keyframes:[{ duration: 0.6, rotation: 0, x: "0%", ease: "power2.in" }, { duration: 0.4, y: "0%", transformOrigin: "center bottom", ease: "sine.in", delay: -0.25 }]}, 1.4)
          .to(".box", { rotateY: 360, ease: "power2.inOut", duration: 0.8 }, 1.6)
          .fromTo(".box__front-face", { webkitFilter: "brightness(1)", filter: "brightness(1)" }, { duration: 0.8, webkitFilter: "brightness(0.2)", filter: "brightness(0.2)", ease: "power4.inOut" }, 1.6)
          .fromTo(".box__right", { webkitFilter: "brightness(1)", filter: "brightness(1)" }, { duration: 0.8, webkitFilter: "brightness(0.8)", filter: "brightness(0.8)", ease: "power4.inOut" }, 1.6)
          .fromTo(".box__lid-flap-shape-outer", { webkitFilter: "brightness(1)", filter: "brightness(1)" }, { duration: 0.4, webkitFilter: "brightness(0.6)", filter: "brightness(0.6)", ease: "power2.in" }, 1.6)
          .to(".box__lid-top-logo", { duration: 0.4, webkitFilter: "brightness(0.6)", filter: "brightness(0.6)", ease: "power2.inOut" }, 1.6)
          .to(".box__lid-flap-shape-outer", { duration: 0.4, webkitFilter: "brightness(1)", filter: "brightness(1)", ease: "power2.inOut" }, 2)
          .set(".box__back", { webkitFilter: "brightness(1)", filter: "brightness(1)", immediateRender:false }, "-=0.8");
        return tl;
      },
      init () {
        const masterTL = gsap.timeline()
        masterTL.add(this.boxIn()).add(this.rotationAnim())
      }
    },
    mounted () {
      this.init()
    }
  }
  </script>
  
  <style lang="scss" scoped>
  $box-width: 180px; // change to change the whole animation size
  $box-height: $box-width*1.387;
  $box-depth: $box-width*0.27355;
  $box-grey: #ececec;
  
  $card-width: $box-width*0.9;
  $card-height: $card-width*1.3944;
  $card-gap: $box-width/50;
  
  html {
    box-sizing: border-box;
  }
  *,
  *:before,
  *:after {
    box-sizing: inherit;
  }
  
  body {
    background: radial-gradient(#ffffff 50%, #d5d3d5 100%);
    overflow: hidden;
  }
  
  body,
  html {
    height: 100%;
    width: 100%;
    margin: 0;
    padding: 0;
  }
  
  .scene {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100%;
    perspective:900px;
    visibility: hidden;
  }
  
  .box {
    transform-style:preserve-3d;
    position: relative;
    z-index: 2;
    width: $box-width;
    height: $box-height;
    transform-style: preserve-3d;
  }
  
  .box__front, .box__back {
    position: absolute;
    width: 100%;
    height:100%;
  }
  
  .box__left, .box__right {
    position: absolute;
    top: 0;
    left: calc(50% - #{$box-depth}/2);
    height: 100%;
    width: $box-depth;
    background: $box-grey;
  }
  
  .box__flap {
    position: absolute;
    left: calc(50% - #{$box-depth}/2);
    top: calc(50% - #{$box-depth}/2);
    width: $box-depth;
    height: 0;
    transform-origin: 50% 100%;
    // create trapezium
    border-bottom: $box-depth solid #dedede;
    border-left: calc(#{$box-depth}/10) solid transparent;
      border-right: calc(#{$box-depth}/10) solid transparent;
  }
  
  .box__lid {
    position: absolute;
    z-index: 0;
    top: calc(50% - #{$box-depth}/2);
    width: $box-width;
    height: $box-depth;
    transform-origin: 50% 100%;
    transform-style: preserve-3d;
    transform: translateZ(calc(-#{$box-depth}/2)) translateY(calc(-#{$box-height}/2 - #{$box-depth}/2 + 0.5px)) rotateY(180deg) rotateX(90deg); 
  }
  
  .box__lid-inner {
    position: relative;
    height: 100%;
    z-index: 0;
    transform-style: preserve-3d;
  }
  
  .box__lid-top {
    width: $box-width;
    height: $box-depth;
    transform-style: preserve-3d;
  }
  
  .box__lid-top-logo {
    position: absolute;
    z-index: 0;
    top: 0;
    left: 0;
    width: $box-width;
    height: $box-depth;
    background: url(https://s3-us-west-2.amazonaws.com/s.cdpn.io/61488/coolclub-logo-full.png) white no-repeat center center;
    background-blend-mode: multiply;
    background-size: cover;
    transform: rotateX(0deg);
    backface-visibility: hidden;
  }
  
  .box__lid-top-back {
    position: absolute;
    left: 0;
    top: 0;
    width: $box-width;
    height: $box-depth;
    background: $box-grey;
    background-image: linear-gradient(-145deg, rgba(0,0,0,0.2) 0%, rgba($box-grey, 0.5) 72%, rgba(white, 0.3) 73% );
    transform: rotateX(180deg);
    backface-visibility: hidden;
  }
  
  .box__lid-flap {
    position: absolute;
    z-index: 0;
    top: calc(50% - #{$box-depth}/2);
    overflow: hidden;
    width: 100%;
    height: 100%;
    transform-origin: 50% 100%;
    transform-style: preserve-3d;
    transform: translateY(calc(-#{$box-depth} + 1px)) rotateX(120deg);
  }
  
  .box__lid-flap-shape {
    position: absolute;
    width: 100%;
    height: 190%;
    border-radius: 50% / 90%;
    overflow: hidden;
    background: $box-grey;
  }
  
  .box__lid-flap-shape-inner {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: $box-grey;
    background: linear-gradient(0deg, rgba(0,0,0,0.3) 0%, rgba(0,0,0,0) 65% );
    // backface-visibility: hidden;
  }
  .box__lid-flap-shape-outer {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: $box-grey;
    transform: rotateX(180deg);
  }
  
  
  .box__flap--left {
    transform: translateX(calc(-#{$box-width}/2)) translateY(calc(-#{$box-height}/2 - #{$box-depth}/2 )) translateZ(0px) rotateY(270deg) rotateX(90deg);
  }
  
  .box__flap--right {
    transform: translateX(calc(#{$box-width}/2)) translateY(calc(-#{$box-height}/2 - #{$box-depth}/2 )) translateZ(0px) rotateY(90deg) rotateX(90deg);
  }
  
  .box__front {
    transform-style: preserve-3d;
    transform: translateZ(calc(-#{$box-depth}/2));
      backface-visibility: hidden;
      
    &:before {
      position: absolute;
      left: 0;
      top: 0;
      content: '';
      width: 100%;
      height: 100%;
      background: #cccbcd;
    }
  }
  
  .box__front-face {
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background: url(https://s3-us-west-2.amazonaws.com/s.cdpn.io/61488/coolclub-front.png) no-repeat left top;
    background-size: cover;
    transform: rotateY( 180deg );
    transform-style: preserve-3d;
    backface-visibility: hidden;
  }
  
  .box__back {
    z-index: 10;
    background: transparent;
    transform: translateZ(calc(#{$box-depth}/2)) rotateY(0deg);
    background: url(https://s3-us-west-2.amazonaws.com/s.cdpn.io/61488/coolclub-back-2.png) no-repeat left top;
    background-size: cover;
  }
  
  .box__left {
    background: url(https://s3-us-west-2.amazonaws.com/s.cdpn.io/61488/coolclub-left.png) no-repeat left top;
    background-size: cover;
    transform: translateX(calc(-#{$box-width}/2)) rotateY(-90deg);
  }
  
  .box__right {
    background: url(https://s3-us-west-2.amazonaws.com/s.cdpn.io/61488/coolclub-right.png) no-repeat left top;
    background-size: cover;
    transform: translateX(calc(#{$box-width}/2)) rotateY(90deg);
  }
  
  
  .box__bottom {
    position: absolute;
    left: 0;
    top: calc(50% - #{$box-depth}/2);
    width: 100%;
    height: $box-depth;
    background: $box-grey;
    transform: translateY(calc(#{$box-height}/2)) rotateX(-90deg);
  }
  
  .card {
    position: absolute;
    left: calc((#{$box-width} - #{$card-width})/2);
    top: 3%;
    width: $card-width;
    height: $card-height;
    background: black;
    backface-visibility: hidden;
    transform-style: preserve-3d;
    
    &:after {
      position: absolute;
      content: '';
      width: 100%;
      height: 100%;
      background: url(https://s3-us-west-2.amazonaws.com/s.cdpn.io/61488/fwa-cards-back.png) no-repeat left top;
      background-size: cover;
      backface-visibility: hidden;
      transform: rotateY( 180deg );
      transform-style: preserve-3d;
    }
  }
  
  .card--1 {
    background: url(https://s3-us-west-2.amazonaws.com/s.cdpn.io/61488/fwa-cards-01.png) no-repeat left top;
    background-size: cover;
    transform: translateZ( 0px) rotateY( 180deg );
  }
  
  .card--2 {
    background: url(https://s3-us-west-2.amazonaws.com/s.cdpn.io/61488/fwa-cards-02.png) no-repeat left top;
    background-size: cover;
    transform: translateZ( $card-gap ) rotateY( 180deg );
  }
  
  .card--3 {
    background: url(https://s3-us-west-2.amazonaws.com/s.cdpn.io/61488/fwa-cards-03.png) no-repeat left top;
    background-size: cover;
    transform: translateZ( $card-gap*2 ) rotateY( 180deg );
  }
  
  .card--4 {
    background: url(https://s3-us-west-2.amazonaws.com/s.cdpn.io/61488/fwa-cards-04.png) no-repeat left top;
    background-size: cover;
    transform: translateZ( $card-gap*3 ) rotateY( 180deg );
  }
  
  .card--5 {
    background: url(https://s3-us-west-2.amazonaws.com/s.cdpn.io/61488/fwa-cards-05.png) no-repeat left top;
    background-size: cover;
    transform: translateZ( $card-gap*4) rotateY( 180deg );
  }
  
  .gsap-3-logo {
    width: 20vw;
    max-width: 150px;
    position: fixed;
    bottom: 15px;
    right: 15px;
  }
  
  /*  ==========================================================
    Collection Linl
    ========================================================== */
  
  .collection {
    position: fixed;
    z-index: 1000;
    top: 24px;
    right: 24px;
    display: flex;
    flex-direction: column;
  }
  
  .collection--1 {
    top: 62px;
  }
  
  .collection__link {
    position: relative;
    margin-bottom: 16px;
    color: black;
    font-family: Helvetica, sans-serif;
    text-decoration: none;
    font-size: 16px;
  
    span {
      display: block;
      position: absolute;
      bottom: -3px;
      left: 0;
      height: 1px;
      width: 10%;
      background-color: black;
      content: "";
      transition: width 0.3s;
    }
  
    &:hover span{
      width: 100%;
    }
  }
  </style>
  