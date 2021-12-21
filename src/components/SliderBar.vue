<template>
  <div class="slider-bar-wrapper">
    <h2>{{ header }}</h2>
    <p v-if="smallText">{{ smallText }}</p>
    <div class="slider-bar">
      <div class="slider-bar-container">
        <div class="ticks">
          <span v-for="n in ticks" :key="n" class="tick"></span>
        </div>
        <div class="slide-bar-wrap">
          <input
              ref="input"
              v-model="currentValue"
              type="range"
              :min="min"
              :max="max"
              class="slider-bar"
              @input="onInput"
          >
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    value: {
      type: Number,
      required: true
    },
    min: {
      type: Number,
      required: true
    },
    max: {
      type: Number,
      required: true
    },
    ticks: {
      type: Number,
      required: true
    },
    header: {
      type: String,
      required: true
    },
    smallText: {
      type: String,
      required: false
    },
  },
  data(){
    return {
      currentValue: this.value
    };
  },
  methods: {
    onInput() {
      this.$emit('input', parseInt(this.currentValue));
    }
  }
};
</script>

<style scoped>
.slider-bar .slider-bar-container {
  width: 100%;
  height: 48px;
  margin-top: 16px;
}

.slider-bar .slider-bar-container .slider-bar {
  -webkit-appearance: none;
  appearance: none;
  width: 100%;
  height: 4px;
  border-radius: 2px;
  background: #000000;
  outline: none;
  opacity: 1;
  margin: 0;
  padding: 0;
}

.slider-bar .slider-bar-container .slider-bar:hover {
  opacity: 1;
}

.slider-bar .slider-bar-container .slider-bar::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 22px;
  height: 48px;
  background: #000000;
  cursor: pointer;
  border-radius: 1px;
  border-style: inset;
  border-color: #a1a1a1;
}

.slider-bar .slider-bar-container .slider-bar::-moz-range-thumb {
  width: 22px;
  height: 48px;
  background: #000000;
  cursor: pointer;
  border-radius: 1px;
  border-style: inset;
  border-color: #a1a1a1;
}

.slide-bar-wrap {
  z-index: 2;
  transform: translateY(-39px);
}

.ticks {
  display: flex;
  align-items: center;
  justify-content: space-between;
  z-index: 11;
}

.tick {
  display: flex;
  justify-content: center;
  width: 4px;
  background: #000000;
  height: 24px;
}

.tick:first-child,
.tick:last-child {
  height: 48px;
}

.slider-bar-wrapper p { margin: 8px 0 0 0; }

@media only screen and (max-width: 600px) {
  .slider-bar-wrapper { text-align: center; }
}

</style>
