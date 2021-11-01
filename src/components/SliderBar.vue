<template>
  <div>
    <div class="slider">
      <div class="slider-container">
        <input
            ref="input"
            v-model="currentValue"
            type="range"
            :min="min"
            :max="max"
            class="slider"
            @input="onInput"
        >
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
    }
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
.slider .slider-container {
  width: 100%;
}

.slider .slider-container .slider {
  -webkit-appearance: none;
  appearance: none;
  width: 100%;
  height: 4px;
  border-radius: 2px;
  background: #c2c2c2;
  outline: none;
  opacity: 0.7;
  -webkit-transition: .2s;
  transition: opacity .2s;
}

.slider .slider-container .slider:hover {
  opacity: 1;
}

.slider .slider-container .slider::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 18px;
  height: 18px;
  background: #D8A22E;
  cursor: pointer;
  border-radius: 50%;
}

.slider .slider-container .slider::-moz-range-thumb {
  width: 18px;
  height: 18px;
  background: #D8A22E;
  cursor: pointer;
  border-radius: 50%;
}
</style>
