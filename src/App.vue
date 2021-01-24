<template>
  <div id="app">
    <div id="cam__flash__base">
      <div id="base__lock">
        <div id="lock__pin" v-for="n in 4" v-bind:key="n.id" />
      </div>
    </div>
    <div id="cam__flash__body">
      <div id="flash__light">
        <div id="light__reflector">
          <div id="reflector__center" />
          <div id="reflector__bulb" />
          <div id="reflector__bulb__filament" />
          <div id="reflector__perspective__top" />
          <div id="reflector__perspective__bottom" />
          <div class="reflector__line__container">
            <div id="reflector__white__lines" v-for="n in 20" v-bind:key="n.id" />
          </div>
          <div class="reflector__line__container">
            <div id="reflector__dark__lines" v-for="n in 10" v-bind:key="n.id" />
          </div>
          <div class="reflector__line__container">
            <div id="reflector__grey__lines" v-for="n in 3" v-bind:key="n.id" />
          </div>
          <div class="reflector__line__container">
            <div id="reflector__black__lines" v-for="n in 15" v-bind:key="n.id" />
          </div>
        </div>
        <div id="q__light">
          q-light
        </div>
        <div id="flash_switch">
          <div id="switch__icon__1" />
          <div id="switch__icon__2" />
          <div id="switch__icon__3" />
          <div id="switch__left__side" />
          <div id="switch__middle__side" />
          <div id="switch__right__side" />
        </div>
      </div>
    </div>
    <div id="cam__body">
      <div id="cam__body__chamfer" />  
      <div id="body__base" />
      <div id="body__base__line" />
      <div id="body__base__middle__line" />
      <div id="body__base__base" />
      <div id="one__step">
        one step
      </div>
      <div id="cam__lens">
        <div id="lens__trapezoid" />
        <div :id="'lens__circles__' + n" v-for="n in 9" v-bind:key="n.id"/>
        <div id="lens__iris">
          <div id="lens__name">
            <div :id="'char__' + index" v-for="(n, index) in myNameIs.split('')" v-bind:key="n.id">
              {{ n }}
            </div>            
          </div>
          <div id="iris__center">
            <div id="iris__center__spot__light" />
          </div>
          <div id="iris__aperture">
            <div :id="'aperture__axis__' + n" v-for="n in 9" v-bind:key="n.id">
            <div class="aperture__section" :style="{ transform: 'rotate(' + rotation + 'rad)'}"/>
            </div>
          </div>
          <div id="iris__spot__light" />          
        </div>
      </div>
      <div id="square__lens" />
      <div id="red__btn" />
      <div id="black__knob" />
      <div id="base__link" />
    </div>

    <div id="cam__base">
      <div id="camera__title">polaroid land camera</div>
      <div id="base__middle__line" />
      <div id="output__contour" />
      <div id="output__contour__perspective" />
    </div>
    
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      myNameIs: 'Henrry Grilo Esposito',
      rotation: 0.9,
      increment: true,
    };
  },
  mounted() {
    this.incrementRotation();
  },
  methods: {
    incrementRotation() {
      if (this.increment) {

        if (this.rotation < 1.8) {
          this.rotation += 0.1;
          setTimeout(() => {
            this.incrementRotation();
          },100);
        }

        else {
          this.rotation -= 0.1;
          setTimeout(() => {
            this.incrementRotation();
          },100);

          this.increment = false
        }
      }

      else {

        if (this.rotation > .9) {
          this.rotation -= 0.1;
          setTimeout(() => {
            this.incrementRotation();
          },100);
        }

        else {
          this.rotation += 0.1;
          setTimeout(() => {
            this.incrementRotation();
          },100);

          this.increment = true;
        }
      }
    },
  }
}
</script>

<style lang="scss">
html {
  background-color: #fef8e2;
  background-repeat: no-repeat;
  background-size: cover;
}
#app {
  display: flex;
  justify-content: center;
  align-items: center;
}
#cam__flash__body {
  height: 140px;
  width: 510px;
  background-color: #fef8e2;
  border: 6px solid  rgb(68, 68, 68);
  border-radius: 20px;
  position: absolute;
  top: 105px;
}
#flash__light {
  height: 150px;
  width: 300px;
  background-color:  rgb(41, 41, 41);
  box-shadow: 0 0 0 2pt  rgb(41, 41, 41);
  border: 6px solid  #fef8e2;
  border-radius: 20px;
  position: absolute;
  top: -90px;
  left: 50%;
  transform: translate(-50%);
}
#light__reflector {
  height: 120px;
  width: 270px;
  background-color: #dbd3b7;
  border-radius: 5px;
  position: absolute;
  top: 15px;
  left: 50%;
  transform: translate(-50%);    
}
#reflector__center {
  height: 90px;
  width: 180px;
  background-color: #f1f1f1;
  border-radius: 2px;
  position: absolute;
  top: 15px;
  left: 50%;
  transform: translate(-50%);
  border-right: 5px solid #fff3e9;
  border-left: 5px solid #fff3e9;
}
#reflector__bulb {
  height: 30px;
  width: 250px;
  background-color: #fdffda;
  border-radius: 50%;
  position: absolute;
  top: 45px;
  left: 50%;
  transform: translate(-50%); 
}
#reflector__bulb__filament {
  height: 3px;
  width: 250px;
  background-color: #858585;
  border-radius: 50%;
  position: absolute;
  top: 58px;
  left: 50%;
  transform: translate(-50%); 
}
#reflector__perspective__top {
  height: 150px;
  width: 215px;
  border-radius: 5px;
  position: absolute;
  left: 20px;
  top: -65px;
  border-right: 8px solid #f8f8f8;
  border-left: 8px solid #f8f8f8;
  transform:  perspective(30em) rotateX(-85deg); 
}
#reflector__perspective__bottom {
  height: 150px;
  width: 215px;
  border-radius: 5px;
  position: absolute;
  left: 20px;
  top: 35px;
  border-right: 8px solid #f8f8f8;
  border-left: 8px solid #f8f8f8;
  transform:  perspective(30em) rotateX(85deg); 
}
.reflector__line__container {
  position: absolute;
  height: 100%;
  width: 100%;
}
#reflector__white__lines {
  margin-top: 3.8px;
  height: 2px;
  width: 100%;
  background-color: #fafafa;
  z-index: 10;
}
#reflector__dark__lines {
  margin-top: 9px;
  height: 2px;
  width: 100%;
  background-color: #e6e6e6;
}
#reflector__grey__lines {
  margin-top: 23px;
  height: 4px;
  width: 100%;
  background-color: #cecece;
}
#reflector__black__lines {
  margin-top: 7px;
  height: 1px;
  width: 100%;
  background-color: #979797;
}
#q__light {
  height: 40px;
  width: 120px;
  border-radius: 8px;
  background-color:  rgb(41, 41, 41);
  position: absolute;
  top: 170px;
  left: -90px;
  color: #f0ebda;
  text-align: center;
  text-transform: capitalize;
  font-style: italic;
  font-size: 18px;
  font-family:'Helvetica';
  line-height: 40px;
}
#flash_switch {
  height: 30px;
  width: 60px;
  border-radius: 8px;
  background: linear-gradient(0deg, rgb(41, 41, 41) 0%, rgb(87, 87, 87) 50%, rgb(41, 41, 41) 100%);
  position: absolute;
  top: 180px;
  right: -50px;
}
#switch__left__side {
  height: 30px;
  width: 24px;
  border-radius: 8px;
  background: linear-gradient(90deg, rgb(87, 87, 87) 0%, rgb(41, 41, 41) 100%);
  position: absolute;
}
#switch__middle__side {
  height: 18px;
  width: 4px;
  border-radius: 8px;
  background-color: rgb(119, 119, 119);
  position: absolute;
  right: 50%;
  transform: translate(50%);
}
#switch__right__side {
  height: 30px;
  width: 24px;
  border-radius: 8px;
  background: linear-gradient(90deg,rgb(41, 41, 41) 0%, rgb(87, 87, 87) 100%);
  position: absolute;
  right: 0;
}
#switch__icon__1 {
  height: 5px;
  width: 5px;
  border-radius: 50%;
  border: 2px solid  rgb(41, 41, 41);
  position: absolute;
  top: -15px
}
#switch__icon__2 {
  
  top: -15px;
  right: 50%;
  transform: translate( 50%);
  position: absolute;
  border-right: 5px solid transparent;
  border-left: 5px solid  transparent;
  border-top: 8px solid  rgb(41, 41, 41);

}
#switch__icon__3 {
  height: 9px;
  width: 9px;
  border-radius: 50%;
  background-color:  rgb(41, 41, 41);
  position: absolute;
  top: -15px;
  right: 0px
}
#cam__flash__base {
  height: 200px;
  width: 530px;
  background-color: rgb(41, 41, 41);
  border-radius: 20px;
  transform: perspective(50em) rotateX(9deg);
  position: absolute;
  top: 130px;
}
#base__lock {
  position: absolute;
  left: -10px;
  top: 185px;
  height: 10px;
  width: 30px;
  border-radius: 25px;
  background-color: rgb(41, 41, 41);
  bottom: 50px;
  display: flex;
}
#lock__pin {
  margin-right: 2px;
  position: relative;
  left: 0;
  top: 0;
  height: 15px;
  width: 50px;
  border-radius: 25px;
  background-color: rgb(41, 41, 41);
  bottom: 50px;
}
#cam__body {
  height: 290px;
  width: 510px;
  border: 6px solid  rgb(68, 68, 68);
  background-color: #fef8e2;
  border-radius: 30px;
  position: absolute;
  top: 270px;
  transform: perspective(50em) rotateX(9deg);
}
#cam__body__chamfer {
  height: 320px;
  width: 490px;
  border: 3px solid #858585;
  border-radius: 20px;
  position: absolute;
  top: 0px;
  left: 7px;
}
#body__base {
  height: 45px;
  width: 522px;
  border-right: 6px solid  rgb(68, 68, 68);
  border-left: 6px solid  rgb(68, 68, 68);
  background-color: #fef8e2;
  position: absolute;
  top: 260px;
  left: -12px;
  transform: perspective(30em) rotateX(30deg);
}
#body__base__middle__line {
  height: 4px;
  width: 450px;
  border-radius: 50%;
  background-color: #858585;
  position: absolute;
  top: 260px;
  left: 28px;
}
#body__base__line {
  height: 55px;
  width: 508px;
  border-right: 3px solid #858585;
  border-left: 3px solid #858585;
  position: absolute;
  top: 252px;
  left: -2px;
  transform: perspective(30em) rotateX(45deg);
}
#body__base__base {
  height: 30px;
  width: 538px;
  border-top: 3px solid #858585;
  border-right: 6px solid  rgb(68, 68, 68);
  border-left: 6px solid  rgb(68, 68, 68);
  border-bottom: 6px solid  rgb(68, 68, 68);
  background-color: #fef8e2;
  border-radius: 10px;
  position: absolute;
  left: -20px;
  top: 300px;
}
#base__link {
  height: 15px;
  width: 524px;
  border-right: 6px solid  rgb(68, 68, 68);
  border-left: 6px solid  rgb(68, 68, 68);
  position: absolute;
  left: -13px;
  top: 335px;
}
#cam__lens {
  height: 200px;
  width: 200px;
  border-radius: 50%;  
  position: absolute;
  top: 25px;
  left: 50%;
  transform: translate(-50%);
  background-color:  rgb(36, 36, 36);
  border: 6px solid #fef8e2;
  box-shadow: 0 0 0 2pt #858585;
}
@for $i from 0 through 9 {
  #lens__circles__#{$i} {
    height: 110px + $i * 10;
    width: 110px + $i * 10;
    border-radius: 50%;  
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    border: 2px solid rgb(32, 32, 32);
  }
}
#lens__trapezoid {
  position: absolute;
  top: 135px;
  left: 27px;
  border-radius: 15px;
  border-bottom: 50px solid rgb(53, 53, 53);
  border-left: 15px solid transparent;
  border-right: 15px solid transparent;
  width: 45px;
  transform: rotateZ(30deg);
  display: flex;
  flex-direction: column-reverse;
}
#lens__iris {
  height: 100px;
  width: 100px;
  border-radius: 50%;  
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color:  rgb(31, 31, 31);
  border-left: 2px solid #fef8e2;
  border-bottom: 2px solid #fef8e2;
}
#lens__name {
  position: absolute;
  top: 50%;
  left: 50%;
  font-size: 6px;
  font-weight: 700;
  color: rgb(75, 75, 75);
}
@for $i from 0 through 20 {
  #char__#{$i} {
    position: absolute;
    padding-top: 43px;    
    transform-origin:0% 0%;
    transform: rotate(2rad - $i / 5);
  }
}
#iris__center {
  height: 12px;
  width: 12px;
  border-radius: 50%;  
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color:  rgb(2, 32, 2);
  border: 8px solid rgb(33, 33, 33);
  box-shadow: 0 0 0 5pt rgb(27, 27, 27);
}
#iris__center__spot__light {
  height: 1px;
  width: 2px;
  border-radius: 50%;  
  position: absolute;
  top: 3px;
  right: 3px;
  background-color: #8d8d8d;
}
#iris__aperture {
  width: 100%;
  height: 100%;
  position: absolute;
  clip-path: circle(50% at 50% 50%);
}
@for $i from 0 through 11{
  #aperture__axis__#{$i} {
    position: absolute;
    top: 50%;
  left: 50%;
    padding-top: 43px;    
    transform-origin:0% 0%;
    transform: rotate(0rad - $i / 1.435);
  }
}
.aperture__section {
  height: 120px;
  width: 120px;
  background: linear-gradient(10deg, rgb(19, 19, 19) 0%, rgb(78, 78, 78) 100%);;
  clip-path: polygon(50% 0%, 0% 100%, 100% 100%);
  transform-origin:50% 0%;
}
#iris__spot__light {
  height: 5px;
  width: 15px;
  border-radius: 50%;  
  position: absolute;
  top: 20px;
  left: 65px;
  background-color: #fef8e2;
  transform: rotateZ(40deg);
}
#one__step {
  height: 50px;
  width: 110px;
  border-radius: 8px;
  background-color:  rgb(41, 41, 41);
  position: absolute;
  top: 100px;
  left: 25px;
  color: #fef8e2;
  text-align: center;
  text-transform: capitalize;
  font-style: italic;
  font-size: 22px;
  font-family:'Helvetica';
  line-height: 50px;
}
#red__btn {
  height: 50px;
  width: 50px;
  border-radius: 50%;
  background-color: #fa7873;
  position: absolute;
  top: 180px;
  left: 50px;
  border: 8px solid #fef8e2;
  box-shadow: 0 0 0 2pt #858585;
}
#black__knob {
  height: 60px;
  width: 60px;
  border-radius: 50%;
  background-color: rgb(41, 41, 41);
  position: absolute;
  top: 185px;
  right: 70px;
}
#square__lens {
  height: 100px;
  width: 100px;
  border-radius: 8px;
  position: absolute;
  top: 25px;
  right: 25px;
  background-color:  rgb(41, 41, 41);
  border: 4px solid #fef8e2;
  box-shadow: 0 0 0 2pt #858585;
}
#cam__base {
  height: 165px;
  width: 565px;
  background-color: rgb(41, 41, 41);
  border-radius: 10px;
  position: absolute;
  top: 627px;
  transform: perspective(30em) rotateX(-5deg);
}
#camera__title {
  padding-top: 35px;
  font-family:'Lucida Console';
  font-weight: 500;
  color: #fef8e2;
  font-size: 20px;
  text-transform: uppercase;
  text-align: center;
}
#base__middle__line {
  height: 4px;
  width: 510px;
  border-radius: 50%;
  background-color: #fef8e2;
  position: absolute;
  top: 20px;
  left: 28px;
}
#output__contour {
  height: 70px;
  width: 530px;
  border-radius: 5px;
  position: absolute;
  top: 70px;
  left: 50%;
  transform: translate(-50%);
  border-right: 3px solid  #fef8e2;
  border-left: 3px solid  #fef8e2;
  border-bottom: 3px solid  #fef8e2;
}
#output__contour__perspective {
  height: 70px;
  width: 495px;
  border-radius: 5px;
  position: absolute;
  left: 33px;
  top: 95px;
  border-right: 3px solid  rgb(92, 92, 92);
  border-left: 3px solid  rgb(92, 92, 92);
  transform:  perspective(30em) rotateX(70deg);
}


</style>
