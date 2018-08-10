<template>
  <div class="home">
    <div class="rect"></div>
    <div class="circle"></div>
    <div class="triangle">
      <div class="item1"></div>
      <div class="item2"></div>
    </div>
    <div class="main">
      <div class="title">
        GEOMETRY PERSON
      </div>
      <div class="sub-title">
        find your core personality type in shapes!
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
export default {
  methods: {},
  mounted() {
    let circle = document.getElementsByClassName('circle')[0];
    let rect = document.getElementsByClassName('rect')[0];
    let triangle = document.getElementsByClassName('triangle')[0];
    let rectDeg = 0;
    let triangleDeg = 0;
    let animate1 = () => {
      rectDeg -= 1;
      rect.style.transform = `translate(-50%, -50%) rotate(${rectDeg}deg)`;
      if (rectDeg > -360) requestAnimationFrame(animate1);
    };
    animate1();
  }
};
</script>
<style lang="scss" scoped>
@mixin centerItem {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
@mixin triangleStyle1 {
  width: 0;
  height: 0;
  border-width: 0 175px 304.5px;
  border-style: solid;
  border-color: transparent transparent #ff3c82;
}
@mixin triangleStyle2 {
  width: 0;
  height: 0;
  border-width: 304.5px 175px 0;
  border-style: solid;
  border-color: #ff3c82 transparent transparent;
}

.home {
  background-color: #1469ff;
  height: 100vh;
  width: 100vw;
}
.rect {
  @include centerItem();
  height: 430px;
  width: 430px;
  background-color: black;
}
.circle {
  width: 539px;
  height: 534px;
  border-radius: 50%;
  background-color: #0027c8;
  @include centerItem();
}
.triangle {
  @include centerItem();
  // transform: translate(-50%, -50%) rotate(120deg);
  .item1 {
    @include triangleStyle1();
    transform: translateY(41%);
  }
  .item2 {
    @include triangleStyle2();
    transform: translateY(-41%);
  }
}
.main {
  @include centerItem();
  text-align: center;
  color: #fff;
  .title {
    font-size: 64px;
    font-weight: bold;
    line-height: 75px;
    white-space: nowrap;
  }
  .sub-title {
    font-size: 24px;
    line-height: 36px;
    white-space: nowrap;
  }
}
</style>
