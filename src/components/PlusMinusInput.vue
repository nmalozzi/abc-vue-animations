<template>
  <div class="plus-minus-input">
    <h2>{{ header }}</h2>
    <div class="plus-minus-button minus" v-on:click="mpminus()">
      -
    </div>
    <div id="field">
      <input type="number" v-model="newValue" :step="step" disabled/>
    </div>
    <div class="plus-minus-button plus" v-on:click="mpplus()">
      +
    </div>
  </div>
</template>

<script>
export default {
  props: {
    header: {
      default: undefined,
      type: String
    },
    value: {
      default: 0,
      type: Number
    },
    min: {
      default: 0,
      type: Number
    },
    max: {
      default: undefined,
      type: Number
    },
    step: {
      default: 1,
      type: Number
    },
  },
  data() {
    return {
      newValue: 0
    }
  },
  methods: {
    mpplus: function () {
      if (this.max === undefined || (this.newValue < this.max)) {
        this.newValue = this.newValue + this.step
        this.$emit('input', this.newValue)
      }
    },
    mpminus: function () {
      if ((this.newValue) > this.min) {
        this.newValue = this.newValue - this.step
        this.$emit('input', this.newValue)
      }
    }
  },
  watch: {
    value: {
      handler: function (newVal) {
        this.newValue = newVal
      }
    }
  },
  created: function () {
    this.newValue = this.value
  }
}
</script>
<style scoped>
.plus-minus-input {
  background-color: #FFF;
  margin: 0 5px 0 5px;
  display: inline-block;
  user-select: none;
}

.plus-minus-input div {
  display: inline-block;
}

.plus-minus-input #field input {
  width: 50px;
  text-align: center;
  font-size: 15px;
  padding: 3px;
  border: none;
}

.plus-minus-input .plus-minus-button {
  padding: 3px 10px 3px 10px;
  cursor: pointer;
  border-radius: 5px;
}

.plus-minus-input .plus-minus-button:hover {
  background-color: #DDD;
}

.plus-minus-input .plus-minus-button:active {
  background-color: #c5c5c5;
}
</style>