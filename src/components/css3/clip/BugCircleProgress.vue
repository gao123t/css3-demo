<template>
  <div class="right-wrap">
    <div class="circle">
      <div class="b"></div>
      <div class="t" :style="setPercent(percent)"></div>
      <div class="p">{{percent}}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BugCircleProgress',
  data: function() {
    return {
      percent: '0'
    }
  },
  methods: {
    setPercent(angle) {
      var finalAngle = ''
      if (angle < 0.5) {
        finalAngle = 'rotate(' + 360 * angle + 'deg)'
        return {
          transform: finalAngle,
          '-webkie-transform': finalAngle,
          backgroundColor: '#ccc'
        }
      } else {
        finalAngle = 'rotate(' + 360 * (angle - 0.5) + 'deg)'
        return {
          transform: finalAngle,
          '-webkie-transform': finalAngle,
          backgroundColor: '#f4436d'
        }
      }
    }
  }
}
</script>

<style lang="scss" scoped>
/* 圆底 */
.right-wrap {
  width: 115px;
  height: 115px;
  position: relative;
  // border-radius: 100%;
  background-clip: padding-box;
  // overflow: hidden;
}

.right-wrap {
  .circle,
  .t,
  .b,
  .p {
    position: absolute;
    width: 120px;
    height: 120px;
    border-radius: 50%;
    z-index: 2;
    overflow: hidden;
  }
  .circle {
    position: relative;

    background-color: #f4436d;
  }
  /* 右半部分 */

  .t {
    width: 120px;
    height: 120px;
    background-color: white;

    clip: rect(0px, auto, auto, 60px);
    -webkit-clip: rect(0px, auto, auto, 60px);

    transform: rotate(0deg);

    background-color: #ccc;
  }

  /* 左半部分 */

  .b {
    width: 120px;
    height: 120px;
    background-color: white;

    clip: rect(auto, 60px, auto, auto);
    -webkit-clip: rect(auto, 60px, auto, auto);

    background-color: #ccc;
  }

  /* 中心白 */

  .p {
    width: 90px;

    height: 90px;

    line-height: 90px;

    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);

    text-align: center;

    border-radius: 50%;

    background-color: #ffffff;
  }
}
</style>
