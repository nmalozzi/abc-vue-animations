<template>
  <div class="output-meter">
    <div class="output-meter-ticks">
      <div v-for="tick in ticks" :key="tick" class="tick">{{ tick }}</div>
    </div>
    <svg class="meter" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 104.5 723" xml:space="preserve"><path d="M95.9 78.5h3v566h-3v-566zm-87.4 0h-3v566h3v-566z" fill="#ccc"/><path d="M17.9 648.2c-3.3-1.1-9.4-5.7-9.4-11.2V88.2c-.8-4.5 6.8-7.9 6.8-7.9.4.2 0 0 0 0l12.5 575.3-9.9-7.4z" opacity=".1" fill="#b3b3b3"/><path d="M55.8 66.2h40.1v502.5H55.8V66.2z" fill="#a6cc75"/><path d="M95.9 568.7v76.4H55.8v-76.4h40.1z" fill="#f9f55a"/><path d="M58.3 578.9v-471c0-3.1-2.1-5.9-5.1-6.7V614c0 1.1-.9 2-2 2s-2-.9-2-2V101.2a7 7 0 0 0-4.9 6.7v471h-4.5v10h4.5v20.8c0 3.9 3.1 7 7 7s7-3.1 7-7v-20.8h4.4v-10h-4.4z" fill="#b3b3b3"/><path d="M51.3 616a2 2 0 0 0 2-2V101.2c-1.3-.4-2.7-.4-4 0V614c0 1.1.9 2 2 2z" fill="#e5e5e5"/><path d="M65.7 586.9h-29c-.5 0-.8.4-.8.8v.2l1.6 7c.1.4.4.6.8.6h1.4v16.7c0 1.6.3 3.2.9 4.8l4 10.2c.3.8 1.1 1.4 2 1.4h9.5c.9 0 1.7-.6 2-1.4l3.8-10.3c.5-1.5.8-3 .8-4.5v-16.9h1.2c.4 0 .7-.2.8-.6l1.8-7c.1-.4-.1-.9-.5-1h-.3z" fill="#999"/><path d="M93 191.5c0-.1-.1-.2-.2-.2H58.7v-12.5H92c.1 0 .2-.1.2-.2s-.1-.2-.2-.2H58.7v-10.7h6.2c.6 0 1-.4 1-1s-.4-1-1-1h-6.2v-14.4h34.1c.1 0 .2-.1.2-.2s-.1-.2-.2-.2H58.7v-12.5H92c.1 0 .2-.1.2-.2s-.1-.2-.2-.2H58.7v-12.1h6.2c.6 0 1-.4 1-1s-.4-1-1-1h-7.2c-.6 0-1 .4-1 1V609c0 .6.4 1 1 1h7.2c.6 0 1-.4 1-1s-.4-1-1-1h-6.2v-37.7h6.2c.6 0 1-.4 1-1s-.4-1-1-1h-6.2V556h34.1c.1 0 .2-.1.2-.2s-.1-.2-.2-.2H58.7v-12.5H92c.1 0 .2-.1.2-.2s0-.9-.2-.9H58.7v-11.9h6.2c.6 0 1-.4 1-1s-.4-1-1-1h-6.2v-13.4h34.1c.1 0 .2-.1.2-.2s-.1-.2-.2-.2H58.7v-12.5H92c.1 0 .2-.1.2-.2s-.1-.2-.2-.2H58.7V489h6.2c.6 0 1-.4 1-1s-.4-1-1-1h-6.2v-12.7h34.1c.1 0 .2-.1.2-.2s-.1-.2-.2-.2H58.7v-12.5H92c.1 0 .2-.1.2-.2s-.1-.2-.2-.2H58.7v-11.5h6.2c.6 0 1-.4 1-1s-.4-1-1-1h-6.2V435h34.1c.1 0 .2-.1.2-.2s-.1-.2-.2-.2H58.7v-12.5H92c.1 0 .2-.1.2-.2s-.1-.2-.2-.2H58.7V410h6.2c.6 0 1-.4 1-1s-.4-1-1-1h-6.2v-13.2h34.1c.1 0 .2-.1.2-.2s-.1-.2-.2-.2H58.7v-12.5H92c.1 0 .2-.1.2-.2s-.1-.2-.2-.2H58.7v-12.9h6.2a1 1 0 0 0 0-2h-6.2v-12.3h34.1c.1 0 .2-.1.2-.2s-.1-.2-.2-.2H58.7v-12.5H92c.1 0 .2-.1.2-.2s-.1-.2-.2-.2H58.7v-13h6.2a1 1 0 0 0 0-2h-6.2v-13.2h34.1c.1 0 .2-.1.2-.2s-.1-.2-.2-.2H58.7v-12.5H92c.1 0 .2-.1.2-.2s-.1-.2-.2-.2H58.7v-11h6.2a1 1 0 0 0 0-2h-6.2v-12.9h34.1c.1 0 .2-.1.2-.2s-.1-.2-.2-.2H58.7v-12.5H92c.1 0 .2-.1.2-.2s-.1-.2-.2-.2H58.7V247h6.2c.6 0 1-.4 1-1s-.4-1-1-1h-6.2v-12.4h34.1c.1 0 .2-.1.2-.2s-.1-.2-.2-.2H58.7v-12.5H92c.1 0 .2-.1.2-.2s0-.5-.2-.5H58.7v-11.7h6.2c.6 0 1-.4 1-1s-.4-1-1-1h-6.2v-13.5h34.1c.1-.1.2-.2.2-.3z" fill="#666"/><path d="M50.8 67.4c27.7 0 42.2 12.3 47.5 18.1 1 1.1.1 2.8-1.5 2.8h-19c-.6 0-1.1-.2-1.5-.6-1.5-1.7-7.1-6.2-24.9-6.2-16.5 0-21.5 4.4-22.9 6.2-.4.4-.9.7-1.5.7H7.5c-1.5 0-2.4-1.6-1.6-2.7 4.5-5.8 17.1-18.3 44.9-18.3zm2.9 588.2c-27.7 0-42.2-12.3-47.5-18.1-1-1.1-.1-2.8 1.5-2.8h19c.6 0 1.1.2 1.5.6 1.5 1.7 7.1 6.2 24.9 6.2 16.5 0 21.5-4.4 22.9-6.2.4-.4.9-.7 1.5-.7h19.4c1.5 0 2.4 1.6 1.6 2.7-4.4 5.8-17 18.3-44.8 18.3z" fill="#f2f2f2"/><path d="M9.2 11.7C30.3-3.8 72-4 94.8 11.7c2.1 1.3 3.3 3.6 3.3 6.1v64.5C80.5 62.7 24.9 62.1 6 82.3V17.6c.1-2.3 1.2-4.5 3.2-5.9zm86.1 699.6c-21.1 15.5-62.8 15.7-85.6 0a7.08 7.08 0 0 1-3.3-6.1v-64.5c17.6 19.6 73.2 20.2 92.1 0v64.7c-.1 2.3-1.3 4.5-3.2 5.9z" fill="gray"/><path d="M99.9 86.8c-1.5 0-2.9-.8-3.8-2-.1-.1-2.8-3.9-9.4-7.6-6.3-3.5-17.6-7.7-35.4-7.7C20.1 69.4 8.1 84 8 84.2a4.45 4.45 0 0 1-6.3.5 4.5 4.5 0 0 1-.7-6.1c.6-.7 14.8-18.1 50.3-18.1 39.3 0 51.8 18.6 52.4 19.4 1.4 2.1.8 4.9-1.3 6.2-.8.4-1.7.7-2.5.7zM52 55.3c-1.4 0-2.5-1.1-2.5-2.5v-44c0-1.4 1.1-2.5 2.5-2.5s2.5 1.1 2.5 2.5v44c0 1.4-1.1 2.5-2.5 2.5zm12.6 1c-1.4 0-2.5-1.1-2.5-2.5v-44c0-1.4 1.1-2.5 2.5-2.5s2.5 1.1 2.5 2.5v44c0 1.4-1.1 2.5-2.5 2.5zm13 3.1c-1.4 0-2.5-1.1-2.5-2.5V13c0-1.4 1.1-2.5 2.5-2.5s2.5 1.1 2.5 2.5v44c0 1.3-1.1 2.4-2.5 2.4zm13.1 5.4c-1.4 0-2.5-1.1-2.5-2.5v-44c0-1.4 1.1-2.5 2.5-2.5s2.5 1.1 2.5 2.5v44c0 1.4-1.2 2.5-2.5 2.5zm-51-8.5c-1.4 0-2.5-1.1-2.5-2.5v-44c0-1.4 1.1-2.5 2.5-2.5s2.5 1.1 2.5 2.5v44c0 1.4-1.1 2.5-2.5 2.5zm-13.1 3.1c-1.4 0-2.5-1.1-2.5-2.5V13c0-1.4 1.1-2.5 2.5-2.5s2.5 1.1 2.5 2.5v44c0 1.3-1.1 2.4-2.5 2.4zm-13 5.4c-1.4 0-2.5-1.1-2.5-2.5v-44c0-1.4 1.1-2.5 2.5-2.5s2.5 1.1 2.5 2.5v44c0 1.4-1.1 2.5-2.5 2.5zm89.2 573.3a4.55 4.55 0 0 0-6.3.7c-.1.2-12.1 14.7-43.2 14.7-17.9 0-29.1-4.2-35.4-7.7-6.6-3.7-9.3-7.5-9.4-7.6-1.4-2.1-4.2-2.7-6.2-1.3s-2.7 4.2-1.3 6.2c.5.8 13 19.4 52.4 19.4 35.4 0 49.7-17.4 50.3-18.1 1.3-1.9 1-4.7-.9-6.3zm-50.3 29.6c-1.4 0-2.5 1.1-2.5 2.5v44c0 1.4 1.1 2.5 2.5 2.5s2.5-1.1 2.5-2.5v-44c0-1.4-1.1-2.5-2.5-2.5zm-12.7-1c-1.4 0-2.5 1.1-2.5 2.5v44c0 1.4 1.1 2.5 2.5 2.5s2.5-1.1 2.5-2.5v-44c0-1.4-1.1-2.5-2.5-2.5zm-13-3.1c-1.4 0-2.5 1.1-2.5 2.5v44c0 1.4 1.1 2.5 2.5 2.5s2.5-1.1 2.5-2.5v-44c0-1.4-1.1-2.5-2.5-2.5zm-13-5.4c-1.4 0-2.5 1.1-2.5 2.5v44c0 1.4 1.1 2.5 2.5 2.5s2.5-1.1 2.5-2.5v-44c0-1.4-1.1-2.5-2.5-2.5zm51 8.5c-1.4 0-2.5 1.1-2.5 2.5v44c0 1.4 1.1 2.5 2.5 2.5s2.5-1.1 2.5-2.5v-44c0-1.4-1.1-2.5-2.5-2.5zm13-3.1c-1.4 0-2.5 1.1-2.5 2.5v44c0 1.4 1.1 2.5 2.5 2.5s2.5-1.1 2.5-2.5v-44c0-1.4-1.1-2.5-2.5-2.5zm13-5.4c-1.4 0-2.5 1.1-2.5 2.5v44c0 1.4 1.1 2.5 2.5 2.5s2.5-1.1 2.5-2.5v-44c0-1.4-1.1-2.5-2.5-2.5z" fill="#757575"/></svg>
    <div
        :style="{maxHeight: waterHeight}"
        class="output-meter-water"
    >
      <div class="svg-wrap">
        <svg class="wave" viewBox="0 0 500 500" preserveAspectRatio="xMinYMin meet">
          <path d="M0,100 C150,200 350,0 500,100 L500,00 L0,0 Z" style="stroke: none; fill:#0197bb;"></path>
        </svg>
        <svg class="bubbles" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 55.69 23.39" xml:space="preserve">
          <circle class="bubble1" cx="10.72" cy="12.67" r="10.72" fill="#aacce0"/>
          <circle class="bubble2" cx="15.34" cy="8.22" r="1.77" fill="#fff"/>
          <circle class="bubble3" cx="37.51" cy="16.55" r="5.89" fill="#aacce0"/>
          <circle class="bubble4" cx="48.25" cy="7.44" r="7.44" fill="#aacce0"/>
          <circle class="bubble5" cx="28.08" cy="5.31" r="5.01" fill="#aacce0"/>
          <circle class="bubble6" cx="26.56" cy="3.96" r="1.7" fill="#fff"/></svg>
      </div>
    </div>
  </div>

</template>

<script>
export default {
  props: {
    output: {
      required: true,
      type: Number
    },
    meterMax: {
      required: true,
      type: Number
    },
    meterMin: {
      default: 1,
      type: Number
    },
    cardinality: {
      default: 13,
      type: Number
    },
  },
  computed: {
    ticks: function () {
      let arr = [];
      const step = (this.meterMax - this.meterMin) / (this.cardinality - 1);
      for (var i = 0; i < this.cardinality; i++) {
        arr.push(Number((this.meterMin + (step * i)).toFixed(1)));
      }
      return arr;
    },
    waterHeight: function () {
      let height = ((554 / (this.cardinality - 1)) * this.output) + 40;
      return height + 'px';
    }
  }
}
</script>

<style scoped>
.output-meter {
  position: relative;
}
.output-meter-ticks {
  position: absolute;
  top: 112px;
  right: -6px;
  display: flex;
  flex-direction: column-reverse;
  justify-content: space-between;
  height: 478px;
  font-size: 14px;
  line-height: 1;
  width: 40px;
  z-index: 100;
}

svg.meter {
  position: relative;
  z-index: 10;
}

.output-meter-water {
  transition: all .5s ease-in-out;
  position: absolute;
  bottom: 76px;
  left: 8px;
  background: #01A0C6;
  width: calc(100% - 14px);
  z-index: 1;
  height: 100%;
  max-height: 1px;
  animation: water 1s ease-in-out 0s infinite alternate;
}

.svg-wrap {
  position: relative;
}

.svg-wrap .wave {
  position: absolute;
  top: 0;
  left: 0;
  height: 80px;
  width: 40px;
}

.svg-wrap .bubbles {
  position: absolute;
  top: -2px;
  left: 2px;
  width: 20px;
}

.svg-wrap .bubbles .bubble1 {
  animation: bubble 16s linear 2s infinite normal;
}

.svg-wrap .bubbles .bubble2 {
  animation: bubble 16s linear 4s infinite normal;
}

.svg-wrap .bubbles .bubble3 {
  animation: bubble 16s linear 3s infinite normal;
}

.svg-wrap .bubbles .bubble4 {
  animation: bubble 16s linear 5s infinite normal;
}

.svg-wrap .bubbles .bubble5 {
  animation: bubble 16s linear 8s infinite normal;
}

.svg-wrap .bubbles .bubble6 {
  animation: bubble 16s linear 6s infinite normal;
}

@keyframes water {
  from { padding-top: -1px; }
  to { padding-top: 1px; }
}

@keyframes bubble {
  0% { opacity: 0; }
  10% { opacity: 1; }
  100% { opacity: 1; }
}

</style>