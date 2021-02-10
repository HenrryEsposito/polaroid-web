<template>
  <div id="photo__view">
    <div id="photo__paper" :class="animate ? 'photo__drop' : ''">
      <div id="photo__frame">
        <div :id="'css__texture__' + cssTexture" />
      </div>
    </div>
    <div id="inner__shadow" />
  </div>
</template>
<script>
export default {
  props: [
    'animate',
  ],
  computed: {
    cssTexture() {
      if (this.animate) {
        return Math.floor(Math.random() * (6)) + 1;
      }
      else {
        return null;
      }
    }
  }
}
</script>
<style scoped>
#photo__view {
  height: 1000px;
  width: 530px;
  position: absolute;
  top: 697px;
  left: 50%;
  transform: translate(-50%);
  overflow: hidden;
  border-top: 1px solid #fef8e225;
}
#inner__shadow {
  width: 100%;
  position: absolute;
  top: 0px;
  left: 50%;
  transform: translate(-50%);
  transform-origin:50% 50%;
  box-shadow: 0 0 20pt 5pt rgb(20, 20, 20);
}
#photo__paper {
  height: 420px;
  width: 350px;
  background-color: #fffcf2;
  position: absolute;
  top: -420px;
  left: 50%;
  transform: translate(-50%);
  transform-origin:50% 50%;
}
.photo__drop {
  animation: drop 4s;
}
@keyframes drop {
  10% {
    top: -420px;
    transform: translate(-50%) perspective(50em) rotateX(70deg);
  }
  60% {
    top: -200px;
    transform: translate(-50%) perspective(50em) rotateX(10deg);
  }
  80% {
    top: -200px;
    transform: translate(-50%) perspective(50em) rotateX(10deg);
  }
  100% {
    top: 300px;
    transform: translate(-50%) perspective(50em) rotateX(-10deg);
  }
}
#photo__frame {
  height: 320px;
  width: 320px;
  background-color: rgb(41, 41, 41);
  position: absolute;
  top: 15px;
  left: 50%;
  transform: translate(-50%);
}
@keyframes reveal {
  0% {
    opacity: 0;
  }
  50% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
#css__texture__1 {
  animation: reveal 4s;
  height: 100%;
  width: 100%;
  background:
    linear-gradient(-45deg, white 25%, transparent 25%, transparent 75%, black 75%, black) 0 0,
    linear-gradient(-45deg, black 25%, transparent 25%, transparent 75%, white 75%, white) 1em 1em,
    linear-gradient(45deg, black 17%, transparent 17%, transparent 25%, black 25%, black 36%, transparent 36%, transparent 64%, black 64%, black 75%, transparent 75%, transparent 83%, black 83%) 1em 1em;
  background-color: white;
  background-size: 2em 2em;
}
#css__texture__2 {
  animation: reveal 4s;
  height: 100%;
  width: 100%;
  background-color: hsl(2, 57%, 40%);
  background-image: repeating-linear-gradient(transparent, transparent 50px, rgba(0,0,0,.4) 50px, rgba(0,0,0,.4) 53px, transparent 53px, transparent 63px, rgba(0,0,0,.4) 63px, rgba(0,0,0,.4) 66px, transparent 66px, transparent 116px, rgba(0,0,0,.5) 116px, rgba(0,0,0,.5) 166px, rgba(255,255,255,.2) 166px, rgba(255,255,255,.2) 169px, rgba(0,0,0,.5) 169px, rgba(0,0,0,.5) 179px, rgba(255,255,255,.2) 179px, rgba(255,255,255,.2) 182px, rgba(0,0,0,.5) 182px, rgba(0,0,0,.5) 232px, transparent 232px),
  repeating-linear-gradient(270deg, transparent, transparent 50px, rgba(0,0,0,.4) 50px, rgba(0,0,0,.4) 53px, transparent 53px, transparent 63px, rgba(0,0,0,.4) 63px, rgba(0,0,0,.4) 66px, transparent 66px, transparent 116px, rgba(0,0,0,.5) 116px, rgba(0,0,0,.5) 166px, rgba(255,255,255,.2) 166px, rgba(255,255,255,.2) 169px, rgba(0,0,0,.5) 169px, rgba(0,0,0,.5) 179px, rgba(255,255,255,.2) 179px, rgba(255,255,255,.2) 182px, rgba(0,0,0,.5) 182px, rgba(0,0,0,.5) 232px, transparent 232px),
  repeating-linear-gradient(125deg, transparent, transparent 2px, rgba(0,0,0,.2) 2px, rgba(0,0,0,.2) 3px, transparent 3px, transparent 5px, rgba(0,0,0,.2) 5px);
}
#css__texture__3 {
  animation: reveal 4s;
  height: 100%;
  width: 100%;
  background-color: hsl(34, 53%, 82%);
  background-image: repeating-linear-gradient(45deg, transparent 5px, hsla(197, 62%, 11%, 0.5) 5px, hsla(197, 62%, 11%, 0.5) 10px,
    hsla(5, 53%, 63%, 0) 10px, hsla(5, 53%, 63%, 0) 35px, hsla(5, 53%, 63%, 0.5) 35px, hsla(5, 53%, 63%, 0.5) 40px,
    hsla(197, 62%, 11%, 0.5) 40px, hsla(197, 62%, 11%, 0.5) 50px, hsla(197, 62%, 11%, 0) 50px, hsla(197, 62%, 11%, 0) 60px,
    hsla(5, 53%, 63%, 0.5) 60px, hsla(5, 53%, 63%, 0.5) 70px, hsla(35, 91%, 65%, 0.5) 70px, hsla(35, 91%, 65%, 0.5) 80px,
    hsla(35, 91%, 65%, 0) 80px, hsla(35, 91%, 65%, 0) 90px, hsla(5, 53%, 63%, 0.5) 90px, hsla(5, 53%, 63%, 0.5) 110px,
    hsla(5, 53%, 63%, 0) 110px, hsla(5, 53%, 63%, 0) 120px, hsla(197, 62%, 11%, 0.5) 120px, hsla(197, 62%, 11%, 0.5) 140px
    ),
  repeating-linear-gradient(135deg, transparent 5px, hsla(197, 62%, 11%, 0.5) 5px, hsla(197, 62%, 11%, 0.5) 10px,
    hsla(5, 53%, 63%, 0) 10px, hsla(5, 53%, 63%, 0) 35px, hsla(5, 53%, 63%, 0.5) 35px, hsla(5, 53%, 63%, 0.5) 40px,
    hsla(197, 62%, 11%, 0.5) 40px, hsla(197, 62%, 11%, 0.5) 50px, hsla(197, 62%, 11%, 0) 50px, hsla(197, 62%, 11%, 0) 60px,
    hsla(5, 53%, 63%, 0.5) 60px, hsla(5, 53%, 63%, 0.5) 70px, hsla(35, 91%, 65%, 0.5) 70px, hsla(35, 91%, 65%, 0.5) 80px,
    hsla(35, 91%, 65%, 0) 80px, hsla(35, 91%, 65%, 0) 90px, hsla(5, 53%, 63%, 0.5) 90px, hsla(5, 53%, 63%, 0.5) 110px,
    hsla(5, 53%, 63%, 0) 110px, hsla(5, 53%, 63%, 0) 140px, hsla(197, 62%, 11%, 0.5) 140px, hsla(197, 62%, 11%, 0.5) 160px
  );
}
#css__texture__4 {
  animation: reveal 4s;
  height: 100%;
  width: 100%;
  background-color:white;
  background-image: linear-gradient(90deg, rgba(200,0,0,.5) 50%, transparent 50%),
    linear-gradient(rgba(200,0,0,.5) 50%, transparent 50%);
  background-size:50px 50px;
}
#css__texture__5 {
  animation: reveal 4s;
  height: 100%;
  width: 100%;
  background-color: #6d695c;
  background-image:
    repeating-linear-gradient(120deg, rgba(255,255,255,.1), rgba(255,255,255,.1) 1px, transparent 1px, transparent 60px),
    repeating-linear-gradient(60deg, rgba(255,255,255,.1), rgba(255,255,255,.1) 1px, transparent 1px, transparent 60px),
    linear-gradient(60deg, rgba(0,0,0,.1) 25%, transparent 25%, transparent 75%, rgba(0,0,0,.1) 75%, rgba(0,0,0,.1)),
    linear-gradient(120deg, rgba(0,0,0,.1) 25%, transparent 25%, transparent 75%, rgba(0,0,0,.1) 75%, rgba(0,0,0,.1));
  background-size: 70px 120px;
}
#css__texture__6 {
  animation: reveal 4s;
  height: 100%;
  width: 100%;
  background:
    radial-gradient(black 3px, transparent 4px),
    radial-gradient(black 3px, transparent 4px),
    linear-gradient(#fff 4px, transparent 0),
    linear-gradient(45deg, transparent 74px, transparent 75px, #a4a4a4 75px, #a4a4a4 76px, transparent 77px, transparent 109px),
    linear-gradient(-45deg, transparent 75px, transparent 76px, #a4a4a4 76px, #a4a4a4 77px, transparent 78px, transparent 109px),
    #fff;
  background-size: 109px 109px, 109px 109px,100% 6px, 109px 109px, 109px 109px;
  background-position: 54px 55px, 0px 0px, 0px 0px, 0px 0px, 0px 0px;
}
</style>